---
description: Audience Manager requires the HTTP server-to-server requests to be digitally signed for validity. This document describes how you can encrypt HTTP requests with private keys.
seo-description: Audience Manager requires the HTTP server-to-server requests to be digitally signed for validity. This document describes how you can encrypt HTTP requests with private keys.
seo-title: Digitally Signed HTTP Requests
solution: Audience Manager
title: Digitally Signed HTTP Requests
uuid: 8da82b7f-46bc-4270-9111-19029e874f7d
index: y
internal: n
snippet: y
translate: y
---

# Digitally Signed HTTP Requests


## Overview {#section_466067C48E9C48AEB2134D9F93DB12A7}

Using a private key provided by you and shared with [!DNL  Audience Manager], we can digitally sign the HTTP requests that are sent between [ IRIS ](../../../c_reference/c_compintro/c_compact.md#section_1966DC17FD14419E943CEF04F13A005B) and your HTTP server. This ensures: 


* **Authenticity**: only the sender that has the private key (IRIS) can send valid HTTP(S) messages to the partner.
* **Message integrity**: with this approach, even on HTTP, you are protected from a man in the middle attack where the messages get distorted.


IRIS has built-in support to rotate the keys with zero downtime, as shown in the [ Rotating the private key ](../../../c_integration/c_outbounding_data/c_outbound_json/digitally_signed_http_requests.md#section_9DDDA6F101784AF0AE7431E99BECAB2A) section below. 

## Information you need to provide {#section_E4A3F5F71908439FA12401C2686A65E6}

For an HTTP real-time server-to-server destination, contact your [!DNL  Audience Manager] consultant and specify: 


* The key used to sign the request.
* The name of the HTTP header that will hold the generated signature (X-Signature in the example header below).
* Optional: the type of hash used for the signature (md5, sha1, sha256).



```
* Connected to partner.website.com (127.0.0.1) port 80 (#0) 
> POST /webpage HTTP/1.1 
> Host: partner.host.com 
> Accept: */* 
> Content-Type: application/json 
> Content-Length: 20 
> X-Signature: wxa2ByMWhhP328EvHQsVlOD5jTc= 
POST message content
```


## How it works {#section_8B0D7BC2F7E449BE823C820EA9143340}


1. IRIS creates the HTTP message to be sent to the partner.
1. IRIS creates a signature based on the HTTP message and the private key communicated by the partner.
1. IRIS sends the HTTP(S) request to the partner. This message contains the signature and the actual message, as seen in the example above.
1. The partner server receives the HTTP(S) request. It reads the message body and the signature received from IRIS.
1. Based on the message body received and the private key, the partner server recalculates the signature. See the [ How to calculate the signature ](../../../c_integration/c_outbounding_data/c_outbound_json/digitally_signed_http_requests.md#section_FFEC0FA7C3274AC5AB492ADD77128E9D) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from IRIS (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. Only the sender, who has the private key, can send a valid signature (authenticity). Moreover, a man in the middle can't modify the message and generate a new valid signature, since they don't have the private key (message integrity).


![](assets/iris-digitally-sign-http-request.png) 

## How to calculate the signature {#section_FFEC0FA7C3274AC5AB492ADD77128E9D}

HMAC (Hash-based message authentication code) is the method used by IRIS for message signing. Implementations and libraries are available basically in every programming language. HMAC has no known extension attacks. See an example in Java below: 


```
// Message to be signed. 
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING 
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY. 
// String getData = "/from-aam-s2s?sids=1,2,3"; 
String postData = "POST message content"; 
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5. 
String algorithm = "HmacSHA1"; 
// Private key shared between the partner and Adobe Audience Manager. 
String key = "sample_partner_private_key"; 
  
// Perform signing. 
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm); 
Mac mac = Mac.getInstance(algorithm); 
mac.init(signingKey); 
byte[] result = mac.doFinal(postData.getBytes()); 
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = wxa2ByMWhhP328EvHQsVlOD5jTc=
```


The RFC for the HMAC hash implementation is [ http://www.ietf.org/rfc/rfc2104.txt ](http://www.ietf.org/rfc/rfc2104.txt). A test site: [ http://asecuritysite.com/encryption/hmac ](http://asecuritysite.com/encryption/hmac) (note that you have to [ convert ](http://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64). 

## Rotating the private key {#section_9DDDA6F101784AF0AE7431E99BECAB2A}

For security reasons, it's recommended to periodically rotate the private key. It is up to you to decide the private key and the rotation period. In order to achieve the key rotation with zero downtime, IRIS supports adding multiple signature headers. One header will contain the signature generated with the old key, another header will contain the signature generated using the new private key. See below the steps in detail: 


1. Partner communicates the new private key to [!DNL  Adobe Audience Manager].
1. IRIS will start sending two signature headers (one using the old key, the other one using the new key).
1. Once you start receiving both headers, you can choose to discard the old key and only look at the new signature.
1. The old key is removed from [!DNL  Audience Manager] and IRIS only sends the new signature header. The keys have been rotated.


## Data used for signing {#section_E68FCC330B3D416FAAB0C4E385EAB116}

For GET type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or HTTP headers - these can be modified / misconfigured along the path or reported incorrectly. 

For POST type destinations, the message used for signing is the *REQUEST BODY*. Again, headers or other request parameters are ignored. 
