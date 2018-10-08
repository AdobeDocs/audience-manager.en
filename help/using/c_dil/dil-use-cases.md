---
description: Code samples and descriptions for specific DIL use cases.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL Use Cases and Code Samples
uuid: 7e915b5c-57c5-4df7-854d-8ab5547583df
index: y
internal: n
snippet: y
translate: y
---

# DIL Use Cases and Code Samples

Code samples and descriptions for specific DIL use cases.

## <wintitle> DIL </wintitle> Use Cases and Code Samples {#concept_5351627A61C24F9C979721E908E2E6C9}

Code samples and descriptions for specific [!UICONTROL DIL] use cases.

<!-- c_dil_use_case.xml -->

## Send Data Elements to Audience Manager with DIL {#concept_83E72615C37B4E4498652C7C1E7EB802}

Create an object variable that sends information about page elements to Audience Manager. This is useful for general data collection or as an alternative to gathering data with Analytics variables.

<!-- c_dil_send_page_objects.xml -->

**Description**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. These examples use a variable to hold data elements in a flat list or an array. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../c_features/traits/trait-variable-prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**Keep Value Properties Consistent**

Remember to keep the value properties the same when passing in data. For example, if you have two identical keys with different values, the value of the last key-value pair takes precedence over the preceding value objects. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**Example 1: Send Data as Key-Value Pairs**

This basic example sends color and price data to Audience Manager in the form of key-value pairs. Your code could look similar to the following: 

```java
var sample_dil = DIL.create({partner:" 
<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
```

**Example 2: Send Data in an Object**

This advanced example demonstrates how to send data in an object to Audience Manager. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] Your code could look similar to the following: 

```java
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : " 
<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
```

**Example 3: Send Page Data in an Array**

In this case, the variable `my_object` uses an array to hold data. This example builds on the information passed in by the recommended method above, but adds an additional layer to accommodate a product type and model. Your code could look similar to the following: 

```java
var my_objects = [{ 
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
>* [signals](dil-instance-methods.md#reference_A651EFE4FB244E748F6E0FB8A4969D08)

## Capture Referring URL {#concept_A362B6D8665A41B8A6E0D4085358FC2D}

Capture and send a referring URL to Audience Manager.

<!-- c_dil_hrefer_over_https.xml -->

>[!NOTE]
>
>This method works only when users move between pages with similar protocols (HTTP vs HTTPS). For example, the browser retains a referring URL when you navigate from a secure site to another secure site. Browsers do not retain the referring URL when you move between secure and unsecure sites. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**Code Sample**

Your code could look similar to the following: 

```java
var adobe_dil = DIL.create({ partner : " 
<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
```

## Capture Search Engine Types and Keyword Search Terms {#concept_146568B1C16B45138E24EA0340737DA9}

Send information about search engine type and keyword searches to Audience Manager.

<!-- c_dil_search_engine_valid.xml -->

**Supported Search Engines**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL] 
* [!DNL Ask] 
* [!DNL Bing] 
* [!DNL Google] 
* [!DNL Yahoo!]

**Description**

The following code demonstrates how to get the search referrer for any of the supported search engines. In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). This code will help you capture those search terms and send them to Audience Manager.

**Basic Code**

Basic code for getting the search referrer (from `google.com`, for example) looks like this: 

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Listed Search Engine Code Sample**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` is a [required prefix](../c_features/traits/trait-variable-prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC) that identifies these as customer-defined variables to Audience Manager. 

```java
var adobe_dil = DIL.create({partner:" 
<i>partner name</i>"}); 
var se = DIL.tools.getSearchReferrer(); 
 
if (se && se.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
```

**Unlisted Search Engine Code Sample**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Your code could look similar to the following: 

```java
var adobe_dil = DIL.create({partner:" 
<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (se && se.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
```

## Map Key Values to Other Keys {#concept_7FE441F32458474286DB9582DF791F1B}

Associate the value from a key-value pair to another key.

<!-- c_dil_map_keys.xml -->

**Description**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. Customer-defined data is used for targeting on the specific site that passed in data on an event call. However, sometimes you want this information available across all properties in your Audience Manager account. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

As an example, you collect ZIP code data from a particular site but want to target it to all your Audience Manager properties. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**Code Sample**

Your code could look similar to the following:

```java
var adobe_dil = DIL.create({ 
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
>* [Prefix Requirements for Key Variables](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)

## Traffic DIL in Google Tag Manager (GTM) {#task_3B7B03F0BA834FDDB3DA9452D1F3318D}

Set up and serve DIL with a GTM tag.

<!-- t_dil_google_tagmanager.xml -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM: 

1. Create a new container or open an existing container.
1. Add a new tag to the container.
1. Open the tag to edit it and:

    * Name the tag. 
    * Select **[!UICONTROL Custom HTML Tag]**from the **[!UICONTROL Tag Type]** drop-down list. 
    
    * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`. 
    
    * Click **[!UICONTROL Save]**.

1. Publish the container.
1. Generate container tag code and place it on your inventory.

>[!MORE_LIKE_THIS]
>
>* [Google Tag Manager Help Center](https://support.google.com/tagmanager#topic=3441530)
