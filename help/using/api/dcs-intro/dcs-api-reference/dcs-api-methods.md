---
description: Send data to the DCS API using GET or POST methods.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API Methods
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
TQID: 'https://experienceleague.adobe.com/dERIW4EM4-oMg8p33N2dtDy5BBw3jF1BCQJstW2cZTY'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
---
# [!DNL DCS] [!DNL API] Methods {#dcs-api-methods}

Send data to the [!DNL DCS] [!DNL API] using `GET` or `POST` methods.

You can send data to the [!DNL DCS] using either one of the `GET` or `POST` methods. Take a look at the sample calls below, using [curl](https://curl.haxx.se/). In all three sample calls, we are adding the signals `c_likes = famous popstar` and `c_loves = famous actress` to the device profile `12345678901234567890123456789012345678`.

## Send Data via [!DNL GET] {#send-data-via-get}

Note that the maximum allowed size for `GET` calls is 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Send Data via [!DNL POST] {#send-data-via-post}

Note the requirements for sending data using the `POST` method:

* The maximum allowed size is 32K.
* Set the content type to `application/x-www-form-urlencoded`.

### Sample call

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
