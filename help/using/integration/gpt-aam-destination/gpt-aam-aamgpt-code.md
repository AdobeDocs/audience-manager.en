---
description: AamGpt is a JavaScript function that reads Audience Manager cookie data and sends that information to Google Publisher Tags.
seo-description: AamGpt is a JavaScript function that reads Audience Manager cookie data and sends that information to Google Publisher Tags.
seo-title: Audience Manager Code for Google Publisher Tags
solution: Audience Manager
title: Audience Manager Code for Google Publisher Tags
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third-party Integration
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
TQID: https://experienceleague.adobe.com/1BiKlAQNtW4-iyx6BT7z1eauizU2TMIVCSS9Z5T9iH8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Audience Manager Code for Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` is a [!DNL JavaScript] function that reads Audience Manager cookie data and sends that information to [!DNL Google Publisher Tags].

>[!NOTE]
>
>This function is not required if you have your own code to read Audience Manager cookie data from the [!UICONTROL UUID] and destination cookies.

## Sample Code

Place the `AamGpt` code at the top of the page, ideally within the `<head>` code block. The `AamGpt` code is available below:

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
