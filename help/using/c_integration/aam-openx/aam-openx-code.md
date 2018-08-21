---
description: Modify OpenX settings to work with Audience Manager segment data.
seo-description: Modify OpenX settings to work with Audience Manager segment data.
seo-title: OpenX Setup
solution: Audience Manager
title: OpenX Setup
uuid: 83b58fb7-d696-4c65-a574-ac4b2cdfbe1e
index: y
internal: n
snippet: y
translate: y
---

# OpenX Setup

To set up OpenX 
* Install DIL code across your site.
* Create OpenX as a cookie destination in Audience Manager.
* Place the ` get_aamCookie` function at the top of the page, ideally within the ` <head>` codeblock. The ` get_aamCookie` code is available [ here ](../../c_features/c_destinations/r_aam_de_cookie.md#reference_0102FABCC96547DE81DFCA0600BBEFD3).
* Modify your ad tag to call the ` get_aamCookie` function and include the cookie name you provided when setting up the OpenX destination. For example, if you named the cookie ` test_cookie`, then the ad tag should call ` get_aamCookie` and reference the cookie name. Your ad tag could look similar example below.
* 
  ```
  <a href= "http://client.adserver.net/?" + get_aamCookie('test_cookie') + 
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Remember to include ` xid=` . It holds the actual unique user ID (UUID) passed in during an ad call. 

The fully formed ad call could look similar to this: 
```
http://client.adserver.net/?c.key1=val1&amp;c.key2=val2&amp;etc&amp; xid =3286487458745343
```

