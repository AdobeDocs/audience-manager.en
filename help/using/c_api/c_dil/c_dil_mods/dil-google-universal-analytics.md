---
description: The GA.submitUniversalAnalytics();function sends data from Google's Universal Analytics to Audience Manager. This DIL function is designed to work with analytics.js, which is the latest code library for Google Universal Analytics.
seo-description: The GA.submitUniversalAnalytics();function sends data from Google's Universal Analytics to Audience Manager. This DIL function is designed to work with analytics.js, which is the latest code library for Google Universal Analytics.
seo-title: GA.submitUniversalAnalytics
solution: Audience Manager
title: GA.submitUniversalAnalytics
uuid: e03ed774-cd03-4f10-9b7d-2a2018dd7437
index: y
internal: n
snippet: y
translate: y
---

# GA.submitUniversalAnalytics



>>[!IMPORTANT]
>>
>>
>>* [!DNL  Audience Manager] does not have any insight into or control over the Google ` analytics.js` code library. You should verify that DIL data collection is still working if or when Google releases new versions of ` analytics.js`.
>>* You cannot use ` GA.submitUniversalAnalytics();` if you're still working with Google's legacy analytics tracking code (e.g., ` ga.js` or ` dc.js`). See [ GA.init ](../../../c_api/c_dil/c_dil_mods/r_dil_ga_init.md#reference_C3DB78CE5C774887AA4FC5629568B651) instead.


>


>**Function Signature:** ` DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);` 

>**Properties** 

>The ` GA.submitUniversalAnalytics();` function accepts the following properties. 



><table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Property </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gaObject </span> </p> </td> 
   <td colname="col2"> <p>The global variable for your instance of Google Analytics. This is usually <span class="codeph"> ga </span> by default, unless you've customized your Google Analytics code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dilInstance </span> </p> </td> 
   <td colname="col2"> <p>The variable that represents your instance of DIL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> internalPropertyName </span> </p> </td> 
   <td colname="col2"> <p> <i>(Optional)</i> In the <span class="codeph"> analytics.js </span> library, the internal property is the minified variable <span class="codeph"> 'b' </span>. This variable holds Google Analytics data. </p> <p>This property is optional because you don't need to set it unless Google changes the name of their internal variable. For example, if this minified variable changed to <span class="codeph"> 'a' </span>, you would call <span class="codeph"> GA.submitUniversalAnalytics(); </span> like this: </p> <p> <span class="codeph"> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

>**Example** 

>Remember to define the Google Analytics ` ga` object first, before calling DIL and ` GA.submitUniversalAnalytics();`. Your code could look similar to this: 

>
>```
>js>//Instantiate DIL 
>var dilInstance = DIL.create({ 
>     partner:"adobe" 
>}); 
> 
>//Call the DIL Universal Analytics function 
>DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
>```

>[!MORE_LIKE_THIS]
>
>* [ GA.init ](r_dil_ga_init.md#reference_C3DB78CE5C774887AA4FC5629568B651)
>* [   ](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
