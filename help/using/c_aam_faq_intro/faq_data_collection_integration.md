---
description: Common data collection and integration questions and issues.
seo-description: Common data collection and integration questions and issues.
seo-title: Data Collection and Product Integration FAQ
solution: Audience Manager
title: Data Collection and Product Integration FAQ
uuid: e3798f9d-b36d-4af3-a34e-95a8740b1553
index: y
internal: n
snippet: y
translate: y
---

# Data Collection and Product Integration FAQ

**How can I differentiate inbound traffic from DCS traffic in DCS log file exports?** 

Traits onboarded via Inbound are populated by Inbound the same way they get populated by DCS. There are a few different ways to tell that traffic came from Inbound: 


* Remote IP will be set to 68.67.173.18
* DomainID will be set to 5325
* Region will be set to 0


**Can you provide me with a list of IP addresses I can white-list for dpm.demdex.net?** 

Unfortunately, we cannot. These IPs are assigned dynamically, by geographic region, through Amazon Web Services. As a result, [!DNL  Audience Manager] does not control the range of IPs that can be assigned to this address. 

**Can you provide me with an IP address I can whitelist for your outbound FTP server?** 

Yes. The egress FTP IP address is 52.44.29.204. 

**What are the code placement and page load requirements for a DIL/Analytics Data Integration?** 

To bring Analytics data into Audience Manager, load DIL after the ` s_code` module but *before* the ` s.t()` function. For example, place your code, or make sure it loads, in this order: 

1. Analytics ` s_code`
1. Audience Manager DIL module
1. Analytics ` s.t()` function
As a best practice, set up your Audience Manager-Analytics integration with either of these 2 methods: 
* Put DIL directly in the ` s_code`.
* Serve DIL and the ` s_code` through Adobe Tag Manager.


See [ Data Integration Library (DIL) API ](../c_api/c_dil/c_dil.md#concept_6D73ED3DBA604EE49B66B5572AA6A32C). 

**Why are my Analytics variables missing from an Audience Manager event call?** 

This usually happens when: 
* You serve DIL through a tag management system that loads it asynchronously with other code elements on the page.
* The ` s.t()` function loads before DIL.


**What versions of Analytics work with DIL?** 

You must use Analytics version 20.2 (or higher) and the Adobe AppMeasurement AS library version 3.5.2 (or higher) to work with DIL. If you don't know your Analytics or AppMeasurement version, check the Analytics call that gets made from the page. Version information shown below: 

This customer uses Analytics version 24.4: 
```
http://112.2o7.net/b/ss/.../1/ 
<b>H.24.4</b>/...
```


This customer uses AppMeasurement version 3.5.2: 
```
http://112.2o7.net/b/ss/.../0/ 
<b>FAS-3.5.2-AS3</b>/...
```


**Can I collect page data if I'm not a Analytics Customer?** 

Yes. The DIL module helps you collect page data even if you're not using Analytics. When set up properly, DIL can capture data from and about: 
* Meta tags
* URLs and URL headers
* Search engine types
* Keywords


Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want DIL to collect data on. This lets you add and remove specific audience data points on your site without any Audience Management updates. Work with your Partner Solutions representative to properly set this up and ensure the DIL module references the page object correctly. 

**Can DIL collect data from Google Analytics?** 

Yes. DIL can collect some Google Analytics (GA) elements and pass that data to Audience Manager. See: 


* [ GA.submitUniversalAnalytics ](../c_api/c_dil/c_dil_mods/dil-google-universal-analytics.md#reference_FF7F8513BEC5457ABE2902BC854C7C18)
* [ GA.init ](../c_api/c_dil/c_dil_mods/r_dil_ga_init.md#reference_C3DB78CE5C774887AA4FC5629568B651)


**Can I get raw data from Audience Manager and how granular is it?** 

Yes, Audience Manager can provide you with data collected for users we've seen on your inventory. This includes: 
* The unique user ID (UUID) assigned by Audience Manager
* Trait and segment IDs
* Unused signals
* Time stamps
* Page URLs


**I want to collect data on one site and target users via a DFP on a different site. Do I need to deploy code on the other property if I don't want to collect data from that location?** 

Yes. Audience Manager DIL code must be on the other site's page to target ads to a user. To target a user in the ad server, we need to send segment information to DFP before the creative loads. To do this, Audience Management code must be on the page where you want to target the user. The code identifies the user and sends that information to DFP. If Audience Manager code is absent from the target page, then we cannot send segments to DFP and target the user based on that data. Without DIL, Audience Manager cannot get segment information to DFP. 

**What is the best third-party data provider?** 

Each provider brings something unique to the table, so the answer depends on what you're looking for. We can enable overlap reporting (at no cost) to help you understand which provider may work best for you. 

**How does Audience Manager set cookies and pass variables to DFP?** 

Audience Manager sets 2 cookies: One sends segment variables to the DFP ad tag and the other sets our unique user ID (UUID), which is also read by DFP. Adding the UUID to the ad tag means we can do user-level reporting and audience discovery. 

**Can we send a DSP information about points in the conversion funnel reached by a user?** 

Yes. We can send funnel data, but the DSP must have the technical capability to use it. A DSP must confirm they can handle multiple segments. If they cannot, we may need to create specific segments to pull a user out of other segments based on their conversion progress (e.g., completed step 1 and 2 but not step 3). You may want to send this information to a DSP so they can retarget users, direct them to a specific landing page, or display specific creatives. 

**How can I confirm that data sent via FTP has been picked up by Audience Manager?** 

A file has been picked up when the extension changes from ` .sync` to ` .processed`. When this happens, the file is in the ingestion queue. Also, your account manager can confirm when a file has been uploaded. 

**I want to test the functionality of the [ DCS API ](https://marketing.adobe.com/resources/help/en_US/aam/dcs-event-calls.html). I am sending event calls like the one shown below. The calls contain [ Declared IDs ](https://marketing.adobe.com/resources/help/en_US/aam/c_declared_id_var_syntax.html) and signals, which should realize some traits and segments I have already set up. Can I use the General Reports and Trend Reports to verify if the trait and segment populations are increasing?** 


```
http://apse2.demdex.net/event?d_rtbd=json&amp;d_cid=123456%01abc123&amp;c_events=placed-an-order
```


No, do not rely on the General Reports and Trend Reports in this case. 

The reports compute populations based on the unauthenticated profile records (UUIDs) we see in the backend at the time the reports are generated. 

On a first call to the DCS, the declared IDs are *not* linked to any UUID (i.e. no [ demdex cookie ](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The DCS will randomly generate a UUID and set a demdex cookie and pass it on in the response call, but it will not transmit the UUID to the backend. 


>[!NOTE]
>
>The generated UUID will only be materialized in our backend data storage once the device on which the cookie is set will trigger further activity.



For this reason, the reports will not reflect the events triggered by the declared IDs in your call. We recommend you use UUID, MID or mobile device IDs in event test calls to the DCS. Then, you can verify the trait and segment realizations in the General Reports and in the Trend Reports. 

See also, the [ Index of Audience Manager IDs ](https://marketing.adobe.com/resources/help/en_US/aam/ids-in-aam.html). 

**How long does it take for user profiles to sync across [ regions ](../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091)?** 

It usually takes up to 24 hours for a user profile to sync across regions. However, in rare cases, the process can take up to 48 hours. 
