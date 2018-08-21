---
description: Modify OAS settings to work with Audience Manager segment data.
seo-description: Modify OAS settings to work with Audience Manager segment data.
seo-title: OAS Setup
solution: Audience Manager
title: OAS Setup
uuid: 0ce1268b-f935-453b-91ec-3468c3a77346
index: y
internal: n
snippet: y
translate: y
---

# OAS Setup

To set up OAS 
* Install DIL code across your site.
* Create OAS as a cookie destination in Audience Manager.
* Place the ` get_aamCookie` function at the top of the page, ideally within the ` <head>` codeblock. The ` get_aamCookie` code is available [ here ](../../c_features/c_destinations/r_aam_de_cookie.md#reference_0102FABCC96547DE81DFCA0600BBEFD3).
* Modify your ad tag to call the ` get_aamCookie` function and include the cookie name you provided when setting up the OAS destination. For example, if you named the cookie ` test_cookie`, then the ad tag should call ` get_aamCookie` and reference the cookie name. Your ad tag could look similar example below.
* 
  ```
  js  <a href= "http://client.adserver.net/?" + get_aamCookie('test_cookie') + 
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Remember to include the ` u=` variable. It holds the actual unique user ID (UUID) passed in during an ad call. 
