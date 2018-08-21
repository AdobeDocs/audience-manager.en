---
description: Create an object variable that sends information about page elements to Audience Manager. This is useful for general data collection or as an alternative to gathering data with Analytics variables.
seo-description: Create an object variable that sends information about page elements to Audience Manager. This is useful for general data collection or as an alternative to gathering data with Analytics variables.
seo-title: Send Data Elements to Audience Manager with DIL
solution: Audience Manager
title: Send Data Elements to Audience Manager with DIL
uuid: db9e4616-3404-4d25-8547-0a93bce80fd6
index: y
internal: n
snippet: y
translate: y
---

# Send Data Elements to Audience Manager with DIL

**Description** 

The following code demonstrates how to collect page data and send it to Audience Manager with DIL. These examples use a variable to hold data elements in a flat list or an array. Remember, pass in variables as [ key-value pairs ](../../../c_reference/c_key_value_explained.md#concept_E4236E003076483AA939791FE2492B49). Also, note the ` c_` prefix before the key in the key-value pair. This [ required prefix ](../../../c_features/c_tb_overview/c_tb_reference/r_tb_variable_prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC) identifies information as user-defined data. In the first example, you need to manually append ` c_` to the key. In the second example, DIL does this for you automatically. 

**Keep Value Properties Consistent** 

Remember to keep the value properties the same when passing in data. For example, if you have two identical keys with different values, the value of the last key-value pair takes precedence over the preceding value objects. For example, passing in ` color:blue` and ` color:red` sets the returned value to red (overwrites blue). 

**Example 1: Send Data as Key-Value Pairs** 

This basic example sends color and price data to Audience Manager in the form of key-value pairs. Your code could look similar to the following: 
```
javavar sample_dil = DIL.create({partner:" 
<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
```


**Example 2: Send Data in an Object** 

This advanced example demonstrates how to send data in an object to Audience Manager. When working with this method, DIL lets you pass an object as a function parameter into the [!DNL  signals()] method. DIL Your code could look similar to the following: 
```
javavar my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : " 
<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
```


**Example 3: Send Page Data in an Array** 

In this case, the variable ` my_object` uses an array to hold data. This example builds on the information passed in by the recommended method above, but adds an additional layer to accommodate a product type and model. Your code could look similar to the following: 
```
javavar my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : " 
<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
```

>[!MORE_LIKE_THIS]
>
>* [ signals ](r_dil_signals.md#reference_A651EFE4FB244E748F6E0FB8A4969D08)
