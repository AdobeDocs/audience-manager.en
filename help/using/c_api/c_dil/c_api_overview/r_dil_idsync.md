---
description: Consists of two functions that let data partners exchange and synchronize user IDs among themselves and Audience Manager.
seo-description: Consists of two functions that let data partners exchange and synchronize user IDs among themselves and Audience Manager.
seo-title: idSync
solution: Audience Manager
title: idSync
uuid: 4f84bae7-d05c-4041-a379-d54b31b82ee6
index: y
internal: n
snippet: y
translate: y
---

# idSync


>**Function Signature:** 

>Works with DIL versions 2.10 and 3.1 or higher. 

><table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Synchronizes User IDs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> dil.Instance.api.idSync(initConfig) </span> </td> 
   <td colname="col2"> <p>Between different data partners and Audience Manager. For example, partner x would use this to synchronize a user ID with partner y and then send that to Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> dil.Instance.api.aamIdSync(initConfig) </span> </td> 
   <td colname="col2"> <p>When you already know the user ID and want to send it to Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

>**idSync Elements** 

>` idSync` can consist of the following: 

><table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> dpid </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Data provider ID assigned by Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> dpuuid </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>The data provider's unique ID for the user. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> minutesToLive </span> </td> 
   <td colname="col2"> Number </td> 
   <td colname="col3"> <p><i>(Optional)</i> Sets the cookie expiration time. Must be an integer. Default is 20160 minutes (14 days). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> url </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Destination URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

>**Macros** 

>` idSync` accepts the following macros: >
>* ** ` %TIMESTAMP%`: **Generates a timestamp (in milliseconds). Used for cache busting.
>* ** ` %DID%`: **Inserts the Audience Manager ID for the user.
>* ** ` %HTTP_PROTO%`: **Sets the page protocol ( ` http` or ` https`).


>**Response** 

>Both functions return ` Successfully queued` if successful. They return an error message string if not. 

>**Sample Code** 

>` dilInstance.api.idSync(initConfig)` >
>```
>js>// Fires url with macros replaced 
>dilInstance.api.idSync({ 
> dpid: '23', // must be a string 
> url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
>%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
> minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
>});
>```


>` dilInstance.api.aamIdSync(initConfig)` >
>```
>js>// Fires 'http:/https:' + '//dpm.demdex.net/ibs:dpid=<dpid>&dpuuid=<dpuuid>' 
>dilInstance.api.aamIdSync({ 
> dpid: '23', // must be a string 
> dpuuid: '98765', // must be a string 
> minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
>});
>```

>[!MORE_LIKE_THIS]
>
>* [  ](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)
