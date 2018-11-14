---
description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modify the GPT setTargeting API Call
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
index: y
internal: n
snippet: y
---

# Modify the GPT setTargeting API Call{#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.

 **Check for Audience Manager Cookies With an IF Statement**

The `.setTargeting` method gets data from the Audience Manager destination cookie and the unique user ID cookie ( `aam_uuid`). However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

**IF Statement Code Sample**

In this example, the Audience Manager destination cookie name is `Sample`. You set this name when you create the destination cookie in the Audience Manager UI. [!UICONTROL DIL] sets the `aam_uuid` cookie and the name cannot be changed. 

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above: 
>
>* Client-side integration: use lines 1-3 only. 
>* Server-side integration: none of the lines are needed. 
>* Ingest [!DNL DFP] log files for reporting in [!DNL Audience Manager]: use lines 4-6 only. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting. 
>

**AamGpt Functions and Data Types**

Defines the key variables used in the `if` statement.  

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Function </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> AamGpt.getKey </span> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Returns the key in the key-value segment pair. For example, if your key-value pair consisted of <span class="codeph"> color=blue </span>, this returns <span class="codeph"> color </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> AamGpt.getValues </span> </p> </td> 
   <td colname="col2"> <p>Array of strings </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <span class="codeph"> ["value1","value2"] </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> AamGpt.getCookie </span> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <span class="codeph"> 12345 </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Create a GPT Destination](../../c-integration/gpt-aam-destination/gpt-aam-create-destination.md#concept_CD39E47404A541719119E9F354EB274C)
>* [Audience Manager Code for Google Publisher Tags](../../c-integration/gpt-aam-destination/gpt-aam-aamgpt-code.md#concept_C47C21701F0F437E823BABF4EB89E1DB)
