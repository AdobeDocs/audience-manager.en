---
description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: 64dfc963-0667-4e6f-beb6-7b45f1d74dff
index: y
internal: n
snippet: y
translate: y
---

# get_aamCookie Code


>` <head>`>
>```
>js><script type="text/javascript"> 
>function get_aamCookie (c_name) 
>{ 
>var i,x,y,ARRcookies=document.cookie.split(";"); 
>for (i=0;i<ARRcookies.length;i++) 
>   { 
>   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("=")); 
>   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1); 
>   x=x.replace(/^\s+|\s+$/g,""); 
>   if (x==c_name) 
>      { 
>      return unescape(y); 
>      } 
>   } 
>} 
></script>
>```

