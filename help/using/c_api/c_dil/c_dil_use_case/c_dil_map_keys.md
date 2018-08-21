---
description: Associate the value from a key-value pair to another key.
seo-description: Associate the value from a key-value pair to another key.
seo-title: Map Key Values to Other Keys
solution: Audience Manager
title: Map Key Values to Other Keys
uuid: 2319d0ab-f3f1-4a5c-bc3a-cdbdcad8d439
index: y
internal: n
snippet: y
translate: y
---

# Map Key Values to Other Keys

**Description** 

In a key-value pair, the ` c_` prefix appended to the key identifies the signal as customer-defined data. Customer-defined data is used for targeting on the specific site that passed in data on an event call. However, sometimes you want this information available across all properties in your Audience Manager account. To do this, map the value in a ` c_` key-value pair to a platform level key. A platform level key is prefixed with ` d_` and makes the signal available for targeting across all properties in your account. 

As an example, you collect ZIP code data from a particular site but want to target it to all your Audience Manager properties. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. ` c_zip`) to a platform defined key as shown below. 

**Code Sample** 

Your code could look similar to the following: 


```
javavar adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_LIKE_THIS]
>
>* [  ](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)
