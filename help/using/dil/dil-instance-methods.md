---
description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
keywords: create traits;create trait
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: Instance-level DIL Methods
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
---
# Instance-level DIL Methods{#instance-level-dil-methods}

The instance-level [!UICONTROL DIL] APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* Access requires a partner name and container namespace ID (NSID). Contact your Audience Manager account manager to obtain this information. 
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you're working with. 

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

Adds customer and platform-level mappings to the query string of a pending request.

<!-- 

r_dil_signals.xml

 -->

**Function Signature:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* You can chain other API calls to this method. 
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request. 

**Reserved Request Keys**

The following request keys are reserved and cannot be overwritten by this method:

* `sids` 
* `pdata` 
* `logdata` 
* `callback` 
* `postCallbackFn` 
* `useImageRequest`

**Parameters** 

|  Name  | Type  | Description |
|---|---|---|
|  `obj`  | Object  | An object representing the key-value pairs for platform-level mappings. Parameter accepts strings and arrays as property values in the object.  |
|  `prefix`  | String  | Optional. The string value prefixed to each object key (replaces original key).  |
|  `return`  | DIL.api  | Returns the API object of the current DIL instance.  |

**Response**

Returns the API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Adds SIDs to the query string of a pending request.

<!-- 

r_dil_traits.xml

 -->

**Function signature:** `traits:function (sids){}`

>[!NOTE]
>
>You can chain other API calls to this method.

**Parameters** 

|  Name  | Type  | Description  |
|---|---|---|
|  `sids`  | Array  | Trait segment IDs in an array.  |

**Response**

Returns the API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Add data to log files in the pending request.

<!-- 

r_dil_logs.xml

 -->

**Function signature:** `logs: function {key1:value1, key2:value2}`

**Response**

Returns the API object of the current [!UICONTROL DIL] instance.

**Sample Code**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## submit {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**Function Signature:** `submit: function () {}`

>[!NOTE]
>
>You can chain other API calls to this method. Also, [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**Response**

Returns the API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

A function that executes after the default destination publishing callback.

<!-- 

r_dil_after_result.xml

 -->

**Function Signature:** `afterResult: function (fn) {}`

>[!NOTE]
>
>You can chain other API calls to this method.

**Parameters** 

|  Name  | Type  | Description  |
|---|---|---|
|  `fn`  | Function  | The function you want to execute after JSON is processed by the default callback that handles destination publishing.  |

**Response**

Returns an API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

Clears all data in a pending request.

<!-- 

r_dil_clear_data.xml

 -->

**Function Signature:** `clearData: function () {}`

>[!NOTE]
>
>You can chain other API calls to this method.

**Response**

Returns the API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Adds custom query parameters that are not explicitly defined by the data collection server to a pending request.

<!-- 

r_dil_custom_query_params.xml

 -->

**Function Signature:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>You can chain other API calls to this method.

**Reserved Request Keys**

The following request keys are reserved and cannot be overwritten by this method:

* `sids` 
* `pdata` 
* `logdata` 
* `callback` 
* `postCallbackFn` 
* `useImageRequest`

**Response**

Returns the API object of the current DIL instance.

**Sample Code** 

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. Useful for debugging and troubleshooting.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Function Signature:** `dil.api.getContainerNSID: function () {}`

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Returns chronologically sorted event log data as an array of strings. Useful for debugging and troubleshooting.

<!-- 

r_dil_get_event_log.xml

 -->

**Function Signature:** `dil.api.getEventLog: function () {}`

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. Useful for debugging and troubleshooting.

<!-- 

r_dil_get_partner.xml

 -->

**Function Signature:** `dil.api.getPartner: function () {}`

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. Useful for debugging and troubleshooting.

<!-- 

r_dil_get_state.xml

 -->

**Function Signature:** `dil.api.getState: function () {}`

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Consists of two functions that let data partners exchange and synchronize user IDs among themselves and Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Function Signature:**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.  

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Synchronizes User IDs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Between different data partners and Audience Manager. For example, partner x would use this to synchronize a user ID with partner y and then send that to Audience Manager. </p> <p> <p><b>Important:</b>  This method is deprecated. Please use the <code> idSyncByURL </code> method of the Adobe Experience Platform Identity Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>When you already know the user ID and want to send it to Audience Manager. </p> <p> <p><b>Important:</b>  This method is deprecated. Please use the <code> idSyncByDataSource </code> method of the Adobe Experience Platform Identity Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` can consist of the following:  

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Data provider ID assigned by Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>The data provider's unique ID for the user. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Number </td> 
   <td colname="col3"> <p><i>(Optional)</i> Sets the cookie expiration time. Must be an integer. Default is 20160 minutes (14 days). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Destination URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macros**

`idSync` accepts the following macros:

* **`%TIMESTAMP%`:** Generates a timestamp (in milliseconds). Used for cache busting. 
* **`%DID%`:** Inserts the Audience Manager ID for the user. 
* **`%HTTP_PROTO%`:** Sets the page protocol ( `http` or `https`).

**Response**

Both functions return `Successfully queued` if successful. They return an error message string if not.

**Sample Code**

`dilInstance.api.idSync(initConfig)` 

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)` 

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## result {#result}

Adds a callback (that receives JSON) to the pending request.

<!-- 

r_dil_result.xml

 -->

**Function Signature:** `result: function (callback) {}`

This callback replaces the default callback that handles destination publishing. 

>[!NOTE]
>
>You can chain other API calls to this method.

**Parameters**

|  Name  | Type  | Description  |
|---|---|---|
|  `callback`  | Function  | JavaScript function executed by the JSONP callback.  |

**Response**

Returns the API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` is a boolean parameter that controls how [!UICONTROL DIL] makes calls to the [!UICONTROL Data Collection Servers (DCS)] and Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls. 

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. See the code sample below.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` is a boolean true/false parameter that controls how the browser requests resources from other domains.

<!-- 

dil-use-cors-only.xml

 -->

**Overview**

`useCORSOnly` is false by default. False means the browser can perform resource checks with CORS or JSONP. However, [!UICONTROL DIL] always tries to request resources with CORS first. It reverts to JSONP on older browsers that do not support CORS. If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**Code Sample**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you're sure that your site visitors have browsers that support this feature. 
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older. 
>

## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Function Signature:** `useImageRequest: function () {}`

>[!NOTE]
>
>You can chain other API calls to this method.

**Response**

Returns an API object of the current [!UICONTROL DIL] instance.

**Sample Code** 

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Name Requirements for Key Variables](../features/traits/trait-key-name-requirements.md)
>* [Prefix Requirements for Key Variables](../features/traits/trait-variable-prefixes.md)
>* [Synchronization Functions in the Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/idsync.html)
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity Service: UseCORSOnly](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [CORS Support in the Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/reference/cors.html)
