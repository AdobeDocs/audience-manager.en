---
description: An overview of DIL and how it works.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
solution: Audience Manager
title: Understanding the Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
---

# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Overview, getting started, and code methods available in the Audience Manager DIL code library.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. It relies on the ID Service to fire ID syncs and URL destinations. An error occurs if the ID Service is missing, old, or not configured. 
>
>We recommend you use Adobe Launch to implement and manage your DIL and Experience Cloud ID Service libraries. However, you can also [download the latest Experience Cloud ID Service release](https://github.com/Adobe-Marketing-Cloud/id-service/releases) from our GitHub page. DIL is not available for public download. Contact your Audience Manager consultant or Customer Care to get the latest DIL version.


## Purpose of DIL {#section_3B99829BBB884E0D9EA5EBE4F55A3F1B}

[!UICONTROL DIL] is an API library. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don't have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md#concept_66CFFEBF5E8B41ED94082D562A93506E). 
* Send data to [destinations](../features/destinations/destinations.md#concept_5BDA346C376C4B719EA394108AB2735A).

## Getting and Implementing DIL Code {#section_C781C1F5E2324F618469C124999CC88A}

[!UICONTROL DIL] code isn't available for download. Contact your consultant to get the latest version. And, please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. It relies on the ID Service to fire ID syncs and URL destinations. An error occurs if the ID Service is missing, old, or not configured.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] is the recommended implementation tool because it simplifies code deployment, placement, and version management. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#section_FBA1B1C0A5704261BD5661EF4EF0276C}

[!UICONTROL DIL] sends data to [!DNL Audience Manager] in an event call. An event call is an XML HTTP request from your page. It uses a `POST` method to send data in the body of the request.

| Event Call Element | Description |
|--- |--- |
|URL|DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`*|
|Body|As shown in sample below,  DIL passes data as key-value pairs. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> 
See also:<ul><li>[Prefix Requirements for Key Variables](../features/traits/trait-variable-prefixes.md)</li><li>
[Supported Attributes for DCS API Calls](../api/dcs-intro/dcs-api-reference/dcs-keys.md)</li></ul>|
