---
description: Send data to the DCS API using GET or POST methods.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API Methods
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
index: y
internal: n
snippet: y
---

# [!UICONTROL DCS] [!UICONTROL API] Methods {#dcs-api-methods}

Send data to the [!UICONTROL DCS] API using `GET` or `POST` methods.

You can send data to the [!UICONTROL DCS] using either one of the `GET` or `POST` methods. Take a look at the sample calls below, using [curl](https://curl.haxx.se/). In all three sample calls, we are adding the signals `c_likes = famous popstar` and `c_loves = famous actress` to the device profile `12345678901234567890123456789012345678`.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Send Data via GET {#section_2F18A1D396334429A2F1C732A8CCEAAD}

Note that the maximum allowed size for `GET` calls is 8K.

```
curl -i "
<i>yourcompany</i>.demdex.net/event?
d_uuid=
<i>12345678901234567890123456789012345678</i>&d_rtbd=json& 
<i>c_likes=famous%20popstar</i>&
<i>c_loves=famous%20actress</i>"
```

## Send Data via POST {#section_AE1A6623F98B44DBB90AA8257D08E2D2}

Note the requirements for sending data using the `POST` method:

* The maximum allowed size is 32K.
* Set the content type to `application/x-www-form-urlencoded`.

### Sample call

```
curl -X POST \ 
  https:// 
<i>yourcompany</i>.demdex.net/event \ 
  -H 'content-type: application/x-www-form-urlencoded' \ 
  -d ' 
<i>c_likes=famous%20popstar</i>& 
<i>c_loves=famous%20actress</i>& 
<i>d_uuid=12345678901234567890123456789012345678</i>'
```

<!-- 

<p> <b>Sample call with content type application/json</b> </p> 
<p> 
 <codeblock>
   curl&nbsp;-X&nbsp;POST&nbsp;\ 
  <discoiqbr />&nbsp;&nbsp;https:// 
  <i>yourcompany</i>.demdex.net/event&nbsp;\ 
  <discoiqbr />&nbsp;&nbsp;-H&nbsp;'content-type:&nbsp;application/json'&nbsp;\ 
  <discoiqbr />&nbsp;&nbsp;-d&nbsp;'{ 
  <i>"c_likes":"famous&nbsp;popstar"</i>, 
  <i>"c_loves":"famous&nbsp;actress"</i>," 
  <i>d_uuid":"12345678901234567890123456789012345678"}</i>' 
 </codeblock> </p>

 -->