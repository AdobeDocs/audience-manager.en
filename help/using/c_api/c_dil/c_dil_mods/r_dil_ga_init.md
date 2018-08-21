---
description: The GA.init() function sends data from the legacy/deprecated version of Google Analytics to Audience Manager.
seo-description: The GA.init() function sends data from the legacy/deprecated version of Google Analytics to Audience Manager.
seo-title: GA.init
solution: Audience Manager
title: GA.init
uuid: fd6e31ee-87ad-4b48-8620-f3a396455970
index: y
internal: n
snippet: y
translate: y
---

# GA.init



>>[!IMPORTANT]
>>
>>` GA.init()` only works with Google's legacy analytics tracking code, ` ga.js` or ` dc.js`. You cannot invoke this DIL function if you use ` analytics.js`, which is the latest code library for Google Universal Analytics. [!DNL  Audience Manager] customers who use DIL and Universal Analytics should see [ GA.submitUniversalAnalytics ](../../../c_api/c_dil/c_dil_mods/dil-google-universal-analytics.md#reference_FF7F8513BEC5457ABE2902BC854C7C18). 
>


>**Function Signature:** ` DIL.modules.GA.init(_gaq, dilInstance, trackVars);` 

>**Parameters** 



>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` _gaq`  | Array  | An array that contains GA commands.  |
>|  ` dilInstance`  | Object  | An object that contains the DIL instance.  |
>|  ` trackVars`  | Object  | *(Optional)* An object that consists of the ` names` property. This property is an array of GA command names that you want to track.  |

>**Supported GA Function Calls** 

>By default, ` GA.init` captures data from the following functions: 

>
>* ` _setCustomVar`
>* ` _addItem`
>* ` _addTrans`
>* ` _setAccount`
>* ` _trackSocial`


>**DIL Creates Keys for GA Data** 

>Audience Manager accepts data in the form of key-value pairs while GA works with items in an array. To work with GA data, DIL creates a key-value pair automatically and forms a key like this: ` c_ <key name>`. Also, items in GA arrays appear in a specific order. As a result, you must supply all parameters in that order, even when they contain no data. DIL maps keys for the following GA methods: >
>```
>js>// Tracking Social Interactions 
>_gaq.push(['_trackSocial', 
>    'facebook',                        // c_socialNetwork 
>    'like',                            // c_socialAction 
>    'http://www.adobe.com/cool.php',   // c_socialTarget 
>    '/cool.php'                        // c_socialPagePath 
>]);  
> 
>// Tracking a Transaction 
>_gaq.push(['_addTrans', 
>   '1234',           // c_transOrderId 
>   'Womens Apparel', // c_transAfflication 
>   '28.28',          // c_transTotal 
>   '1.29',           // c_tranTax 
>   '15.00',          // c_transShipping 
>   'San Jose',       // c_transCity 
>   'California',     // c_transState 
>   'USA'             // c_transCountry 
>]); 
> 
>// Tracking an item 
>_gaq.push(['_addItem', 
>   '1234',           // c_itemOrderId=1234 
>   'DD44',           // c_itemSku 
>   'T-Shirt',        // c_itemName 
>   'Olive Medium',   // c_itemCategory 
>   '11.99',          // c_itemPrice 
>   '1'               // c_itenQuantity 
>]);
>```


>**Sample Code** >
>```
>js>// DIL JavaScript library needs to be loaded and executed here 
>var dilInstance = DIL.create({ 
>    partner : "adobe" 
>}); 
> 
>// Assume ga.js has not loaded 
>var _gaq = _gaq || []; 
>_gaq.push( 
>  ['_setAccount', 'UA-XXXXX-X'], 
>  ['_setDomainName', 'example.com'], 
>  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
>  ['_trackPageview'] 
>); 
>_gaq.push([ 
>  '_addItem', 
>  '1234',         // order ID - necessary to associate item with transaction 
>  'DD44',         // SKU/code - required 
>  'T-Shirt',      // product name - necessary to associate revenue with product 
>  'Olive Medium', // category or variation 
>  '11.99',        // unit price - required 
>  '1'             // quantity - required 
>]); 
>
>```


>To track all the monitored GA metrics without the additional function shown above, invoke ` GA.init` by itself like this: 

>` DIL.modules.GA.init(_gaq, dilInstance).submit();` 

>**Sample Event Call** 

>The URL event call to Audience Manager could look similar to this: 

>` http://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&amp;c_Section=Life%20%26%20Style &amp;c_itemOrderId=1234&amp;c_itemSku=DD44&amp;c_itemName=T-Shirt&amp;c_itemCategory=Olive%20Medium&amp; c_itemPrice=11.99&amp;c_itemQuantity=1` 
>[!MORE_LIKE_THIS]
>
>* [ GA.submitUniversalAnalytics ](dil-google-universal-analytics.md#reference_FF7F8513BEC5457ABE2902BC854C7C18)
>* [  ](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [  ](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [  ](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
