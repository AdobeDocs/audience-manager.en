---
description: You can send qualified segments to DFP either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-description: You can send qualified segments to DFP either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to DFP Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Requirements and Methods of Sending Segments to DFP Using Google Publisher Tags (GPT)
uuid: 34f8a0bc-f991-40e6-8e55-b41b380b4da9
index: y
internal: n
snippet: y
translate: y
---

# Requirements and Methods of Sending Segments to DFP Using Google Publisher Tags (GPT)


<ul class="simplelist"> 
 <li> <a href="../../c_integration/gpt-aam-destination/gpt-aam-requirements.md#section_8F4B25C64A914B3A9A6FEEA95F5CEF9B" format="dita" scope="local"> Client-Side Integration </a> </li> 
 <li> <a href="../../c_integration/gpt-aam-destination/gpt-aam-requirements.md#section_3E1127403A184C7D84B3FA1A1B917A62" format="dita" scope="local"> Server-Side Integration </a> </li> 
</ul>



## Client-Side Integration {#section_8F4B25C64A914B3A9A6FEEA95F5CEF9B}

For a client-side integration, you need to set up a GPT destination in Audience Manager. Consider the following points when you want to set up GPT as an Audience Manager destination: 


* **Add DIL:** Deploy Data Integration Library (DIL) code on all the pages you want to target. DIL writes Audience Manager segment data and user IDs to cookies that get used by GPT for targeting.
* **Create a Cookie Destination:** GPT must be set up as a cookie-based destination in Audience Manager.
* **Implement Cookie Checking Code:** Wrap the GPT ` .setTargeting` API method in our recommended [ cookie checking code ](../../c_integration/gpt-aam-destination/gpt-aam-modify-api.md#concept_276DF2F702BE4D6180C855A7DE304097). This code helps prevent errors by looking for valid AAM cookies before the ` .setTargeting` method gets invoked.
* **Add the AamGpt Function:** The ` AamGpt` code captures data from Audience Manager cookies and sends it to GPT. Place the [ Audience Manager Code for Google Publisher Tags ](../../c_integration/gpt-aam-destination/gpt-aam-aamgpt-code.md#concept_C47C21701F0F437E823BABF4EB89E1DB) ( ` AamGpt`) at the top of the page or inside the ` <head>` codeblock. 
  >[!NOTE]
  >
  >The ` AamGpt` function is not required if you use your own code to read Audience Manager cookie data. 

* **Send Delivery Logs to Audience Manager:** If you want a segment delivery report (optional), provide Audience Manager with a daily log that contains impression-level delivery data. The data can be in a raw format, but each record must contain the Audience Manager UUID. Audience Manager can pick up or receive these via FTP.


**Only Qualified Segments are Sent to GPT** 

The amount of data passed in to GPT depends on how many segments a particular user qualifies for. For example, say you set up 100 Audience Manager segments. If a site visitor qualifies for five of them, then only those five segments get sent to GPT (not all 100). 


>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the Google request URL does have limits to the number of characters it can accept. See[ Setting targeting and sizes with GPT ](http://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712). 



## Server-Side Integration {#section_3E1127403A184C7D84B3FA1A1B917A62}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with DFP, using GPT. You'll need to provide your DFP account Network Id and Audience Link Id. 


>[!IMPORTANT]
>
>If your web pages are running the[ Accelerated Media Pages ](https://www.ampproject.org/) (AMP) library, you must use the server-side integration with Audience Manager. If you are on AMP and have a client-side integration with AMP, you must migrate to the server-side integration. Please contact your Audience Manager consultant or Customer Care to discuss migration. 


>[!MORE_LIKE_THIS]
>
>* [  ](http://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
