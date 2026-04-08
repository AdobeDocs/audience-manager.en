---
description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
TQID: https://experienceleague.adobe.com/x8w8GMRG9gnMWQAXyaWdguFk1SaD7P-199ccfyIQf-s
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
subfeature_v2:
  - id: c138d302-73f0-4186-93ea-10c4ba52f943
    internal-label: Destination basics
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
    internal-label: Destination Builder
---
# `get_aamCookie` Code {#get-aamcookie-code}

Code required by [!DNL DART Enterprise] (and other destination types) to capture the Audience Manager unique user ID ([!DNL UUID]) value.

Define this function at the top of the page, ideally within the `<head>` code block.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
