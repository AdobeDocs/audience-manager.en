---
description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: d0813ed9-b914-4183-8fb3-88c72323959a
index: y
internal: n
snippet: y
translate: y
---

# get_aamCookie Code

Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.

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

