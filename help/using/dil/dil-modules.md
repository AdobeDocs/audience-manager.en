---
description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL Modules
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
---

# DIL Modules{#dil-modules}

Describes methods in the `DIL.modules` namespace. These modules let you programmatically collect data and work with Audience Manager objects.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Works with [!UICONTROL DIL] to send [!DNL Analytics] tag elements (variables, props, eVars, etc.) to Audience Manager. Returns data in a comma separated list. Available in version 2.6. 

**Function Signature:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>You must place this code on the page *before* the `s.t();` function.

<!-- 

r_dil_sc_init.xml

 -->

**Parameters**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Names </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>An array of strings that contains un-enumerated <span class="keyword"> Analytics </span> variables like <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>An array of objects that contains enumerated <span class="keyword"> Analytics </span> variables like props and evars (e.g. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Integer </td> 
   <td colname="col3"> <p>Indicates how many iterated names you want to return. For example, to return two props or evars, set <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>An object that represents the <span class="keyword"> Analytics </span> object. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>An object that represents <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Additional options: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>If you do not specify something else, periods are replaced with the default underscore ( _ ). </p> <p>For example <code> s.contextData = {abc.def = '123'} </code>would result in <code> c_contextData_abc_def=123 </code> in the event call query string. </p> <p>This option is available only in <span class="wintitle"> DIL </span> version 5.0 or later. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>For example, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> would result in the array of strings being filtered from the data collection of context data. This option excludes Personally Identifiable Information (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Data Captured by siteCatalyst.init**

This function returns details on the following [!DNL Analytics] properties:

* `pageName` 
* `channel` 
* `campaign` 
* `products` 
* `events` 
* `eVar` (1 - 250) 
* `prop` (1 - 75) 
* `pe` 
* `pev1` 
* `pev2` 
* `pev3`

**Sample Code**

This code creates a comma separated list of [!DNL Analytics] events (props, eVars, etc.) if values for them exist. 

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

To track all the monitored [!DNL Analytics] data points without the additional function shown above, invoke `siteCatalyst.init` by itself like this: 

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

The `GA.submitUniversalAnalytics();` function sends data from Google's [!DNL Universal Analytics] to Audience Manager. This [!UICONTROL DIL] function is designed to work with `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] does not have any insight into or control over the Google `analytics.js` code library. You should verify that [!UICONTROL DIL] data collection is still working if or when Google releases new versions of `analytics.js`. 
>
>* You cannot use `GA.submitUniversalAnalytics();` if you're still working with Google's legacy analytics tracking code (e.g., `ga.js` or `dc.js`). See [GA.init](../dil/dil-modules.md#ga-init) instead. 
>

**Function Signature:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Properties**

The `GA.submitUniversalAnalytics();` function accepts the following properties.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Property </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>The global variable for your instance of <span class="keyword"> Google Analytics </span>. This is usually <code> ga </code> by default, unless you've customized your <span class="keyword"> Google Analytics </span> code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>The variable that represents your instance of <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optional)</i> In the <code> analytics.js </code> library, the internal property is the minified variable <code> 'b' </code>. This variable holds <span class="keyword"> Google Analytics </span> data. </p> <p>This property is optional because you don't need to set it unless Google changes the name of their internal variable. For example, if this minified variable changed to <code> 'a' </code>, you would call <code> GA.submitUniversalAnalytics(); </code> like this: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

Remember to define the [!DNL Google Analytics] `ga` object first, before calling [!UICONTROL DIL] and `GA.submitUniversalAnalytics();`. Your code could look similar to this:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_LIKE_THIS]
>
>* [ga Object Methods Reference](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

## GA.init {#ga-init}

The `GA.init()` function sends data from the legacy/deprecated version of [!DNL Google Analytics] to Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` only works with Google's legacy analytics tracking code, `ga.js` or `dc.js`. You cannot invoke this [!UICONTROL DIL] function if you use `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics]. [!DNL Audience Manager] customers who use [!UICONTROL DIL] and [!DNL Universal Analytics] should see [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Function Signature:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameters**

|  Name  | Type  | Description  |
|---|---|---|
|  `_gaq`  | Array  | An array that contains GA commands.  |
|  `dilInstance`  | Object  | An object that contains the DIL instance.  |
|  `trackVars`  | Object  | *(Optional)* An object that consists of the `names` property. This property is an array of GA command names that you want to track.  |

**Supported GA Function Calls**

By default, `GA.init` captures data from the following functions:

* `_setCustomVar` 
* `_addItem` 
* `_addTrans` 
* `_setAccount` 
* `_trackSocial`

**DIL Creates Keys for GA Data**

Audience Manager accepts data in the form of key-value pairs while GA works with items in an array. To work with GA data, [!UICONTROL DIL] creates a key-value pair automatically and forms a key like this: `c_ <key name>`. Also, items in GA arrays appear in a specific order. As a result, you must supply all parameters in that order, even when they contain no data. [!UICONTROL DIL] maps keys for the following GA methods: 

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Sample Code** 

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 

```

To track all the monitored GA metrics without the additional function shown above, invoke `GA.init` by itself like this:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Sample Event Call**

The URL event call to Audience Manager could look similar to this:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1` 

>[!MORE_LIKE_THIS]
>
>* [Google Analytics Tracking Code](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Complete Web Upgrade: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [Adding analytics.js to Your Site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
