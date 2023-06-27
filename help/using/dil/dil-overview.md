---
description: An overview of DIL and how it works.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Understanding the Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
---
# Understanding the [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Starting with July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the DIL extension.
><br><br>Existing customers can continue using their DIL implementation, but no support will be provided after this date.
><br><br>Customers looking to implement new data collection integrations should use the [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

Overview, getting started, and code methods available in the [!DNL Audience Manager DIL] code library.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 or higher. It relies on the [!DNL ID Service] to fire ID syncs and URL destinations. An error occurs if the [!DNL ID Service] is missing, old, or not configured. 
>
>We recommend you use [!DNL Adobe Experience Platform Tags] to implement and manage your [!DNL DIL] and [!DNL Adobe Experience Platform Identity Service] libraries.

However, you can also download the latest Experience Cloud and [!DNL DIL] releases from our GitHub page. See download links below:

* Download the [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] is an API library. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don't have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md). 
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] code is available for download **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 or higher. It relies on the [!DNL ID Service] to fire ID syncs and [!DNL URL destinations]. An error occurs if the [!DNL ID Service] is missing, old, or not configured.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) instead. [!DNL Adobe Experience Platform Tags] is the recommended implementation tool because it simplifies code deployment, placement, and version management. Read more about the [Audience Manager extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Sample Call {#sample-code}

[!UICONTROL DIL] sends data to [!DNL Audience Manager] in an event call. An event call is an XML HTTP request from your page. It uses a `POST` method to send data in the body of the request.

| Event Call Element | Description |
|--- |--- |
|URL|DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`*|
|Body|As shown in sample below,  DIL passes data as key-value pairs. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br>|

See also:
* [Prefix Requirements for Key Variables](../features/traits/trait-variable-prefixes.md)
* [Supported Attributes for DCS API Calls](../api/dcs-intro/dcs-api-reference/dcs-keys.md)
  
## Related Links

* [DIL Use Cases and Code Samples](/help/using/dil/dil-use-cases.md)
* [Class-level DIL Methods](/help/using/dil/dil-class-overview/dil-start.md)
* [Instance-level DIL Methods](/help/using/dil/dil-instance-methods.md)
* [DIL Modules](/help/using/dil/dil-modules.md)
* [DIL Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
