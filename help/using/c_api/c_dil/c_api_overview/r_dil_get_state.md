---
description: Returns the state of the current DIL instance. Useful for debugging and troubleshooting.
seo-description: Returns the state of the current DIL instance. Useful for debugging and troubleshooting.
seo-title: getState
solution: Audience Manager
title: getState
uuid: 8932cf55-0ef0-48ff-90cc-efe93171f2f4
index: y
internal: n
snippet: y
translate: y
---

# getState


>**Function Signature:** ` dil.api.getState: function () {}` 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName</i>', 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>dataLib.api.traits([ 
<i>123, 456, 789</i>]).logs({ 
>     file: 'dil.js', 
>     message:'This is the first request' 
>});.signals({ 
>     c.zdid:  
<i>1111</i> 
>     d_dma: ' 
<i>default</i>' 
>});.submit(); 
> 
>var state = dataLib.api.getState(); 
> 
>/*Object outline of state 
>state = { 
>     pendingRequest: { 
<i>pending data for call to server</i>}, 
>     otherRequestInfo:{ 
>          firingQueue: [], 
>          fired: [], 
>          firing: false, 
>          errored: [], 
>          reservedKeys: { 
>               sids: true, 
>               pdata: true, 
>               logdata: true, 
>               callback: true, 
>               postCallbackFn: true, 
>               useImageRequest: true, 
>          }, 
>          firstRequestHasFired: false, 
>          num_of_jsonp_responses: 0, 
>          num_of_jsonp_errors: 0, 
>          num_of_img_responses: 0, 
>          num_of_img_errors: 0 
>     }, 
>     destinationPublishingInfo: { 
>          THROTTLE_START: 3000, 
>          throttleTimerSet: false, 
>          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
>          url: (constants.isHTTPS ? 'https://' : 'http://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
>          + containerNSID + '#' + encodeURIComponent(document.location.href), 
>               iframe: null, 
>               iframeHasLoaded: false, 
>               sendingMessages: false, 
>               messages: [], 
>               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
>               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
>               jsonProcessed: [] 
>     } 
>} 
>*/
>```

