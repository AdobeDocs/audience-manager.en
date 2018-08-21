---
description: Works with DIL to send Analytics tag elements (variables, props, eVars, etc.) to Audience Manager. Returns data in a comma separated list. Available in version 2.6.
seo-description: Works with DIL to send Analytics tag elements (variables, props, eVars, etc.) to Audience Manager. Returns data in a comma separated list. Available in version 2.6.
seo-title: siteCatalyst.init
solution: Audience Manager
title: siteCatalyst.init
uuid: c8efa446-bca9-4468-bc49-4309f649af40
index: y
internal: n
snippet: y
translate: y
---

# siteCatalyst.init


>**Function Signature:** ` DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)` 

>>[!NOTE]
>>
>>You must place this code on the page*before* the ` s.t();` function. 
>
>**Parameters** 



><table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Names </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> names </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>An array of strings that contains un-enumerated Analytics variables like <span class="codeph"> pageName </span>, <span class="codeph"> channel </span>, <span class="codeph"> campaign </span>, <span class="codeph"> product </span>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> iteratedNames </span> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>An array of objects that contains enumerated Analytics variables like props and evars (e.g. <span class="codeph"> prop1 </span>, <span class="codeph"> prop2 </span>, <span class="codeph"> evar3 </span>, <span class="codeph"> evar4 </span>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> maxIndex </span> </td> 
   <td colname="col2"> Integer </td> 
   <td colname="col3"> <p>Indicates how many iterated names you want to return. For example, to return two props or evars, set <span class="codeph"> maxIndex:2 </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> siteCatalystReportingSuite </span> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>An object that represents the Analytics object. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> dilInstance </span> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>An object that represents DIL. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> options </span> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Additional options: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <span class="codeph"> replaceContextDataPeriodsWith </span> </p> <p>If you do not specify something else, periods are replaced with the default underscore ( _ ). </p> <p>For example <span class="codeph"> s.contextData = {abc.def = '123'} </span>would result in <span class="codeph"> c_contextData_abc_def=123 </span> in the event call query string. </p> <p>This option is available only in DIL version 5.0 or later. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <span class="codeph"> filterFromContextVariables </span> </p> <p>For example, <span class="codeph"> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </span> would result in the array of strings being filtered from the data collection of context data. This option excludes Personally Identifiable Information (PII). </p> </li> 
    </ul> <p></p> </td> 
  </tr> 
 </tbody> 
</table>

>**Data Captured by siteCatalyst.init** 

>This function returns details on the following Analytics properties: >
>* ` pageName`
>* ` channel`
>* ` campaign`
>* ` products`
>* ` events`
>* ` eVar` (1 - 250)
>* ` prop` (1 - 75)
>* ` pe`
>* ` pev1`
>* ` pev2`
>* ` pev3`


>**Sample Code** 

>This code creates a comma separated list of Analytics events (props, eVars, etc.) if values for them exist. >
>```
>// Get the Site Catalyst object instance: 
>var s = s_gi(s_account); 
>  
>// Instantiate DIL code: 
>var scDil = DIL.create({ 
>        partner: 'adobe', 
>        containerNSID: 5 
>}); 
> 
>// Use the module: 
>DIL.modules.siteCatalyst.init(s, scDil, { 
>        //Specify the Site Catalyst variables you want to capture: 
>        names: ['pageName', 'channel', 'campaign'], 
>        //Use this to create iterated variable names: 
>        iteratedNames: [{ 
>               name: 'eVar', 
>               maxIndex: 75 
>        }, { 
>               name: 'prop', 
>               maxIndex: 75 
>        }] 
>});
>```


>To track all the monitored Analytics data points without the additional function shown above, invoke ` siteCatalyst.init` by itself like this: >
>```
>DIL.modules.siteCatalyst.init(s, scDil);
>```



