---
description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implement the Audience Management Module
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
---
# How to forward data from [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

Follow the steps in this tutorial to forward [!DNL Analytics] data to [!DNL Audience Manager] instead of having the [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) code send a pixel from the page.

>[!TIP]
>
>We recommend you use [!DNL Adobe Experience Platform Launch] to forward [!UICONTROL Analytics] data into [!DNL Audience Manager]. By using [!UICONTROL Launch], you do not have to manually copy code into [!DNL AppMeasurement], as shown on this page.

## Prerequisites {#prereqs}

In addition to enabling the extensions or implementing the code described in this document, you must also:

* Implement the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
* Enable [Server-Side Forwarding](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implementation {#implementation}

There are two methods to implement data forwarding from [!DNL Adobe Analytics] to [!DNL Audience Manager], depending on the tag management solution that you use.

### Implementation using [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recommends you use the [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) extension to instrument [!DNL Adobe Analytics] and [!DNL Audience Manager] on your properties. In this case, you do not need to manually copy any code. Instead, you must enable data sharing in the [!DNL Analytics Launch] extension, as shown in the image below. See also the [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) documentation.

>[!TIP]
>
>If you install the [!DNL Adobe Analytics] extension, *do not* also install the [!DNL Audience Manager] extension. Forwarding data from the [!DNL Analytics] extension replaces the [!DNL Audience Manager] extension functionality.

![How to enable data sharing from the Adobe Analytics extension to Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Code Elements Defined {#code-elements-defined}

The following table defines important variables in the code sample.

| Parameter | Description |
|--- |--- |
|`partner`|Required. This is a partner name assigned to you by [!DNL Adobe]. It is sometimes referred to as your [!UICONTROL partner ID] or partner subdomain.  Contact your [!DNL Adobe] consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don't know your partner name.|
|`containerNSID`|Required. Most customers can just set  `"containerNSID":0` . However, if your company needs to customize ID syncs with a different container, you can specify that container ID here.|
|`uuidCookie`|Optional. This configuration lets you set an [!DNL Adobe] cookie in the first-party domain. This [!DNL cookie] contains the [UUID](../../reference/ids-in-aam.md) .|
| `visitorService` - `namespace`| Required. The `namespace` parameter is required if you use the [!DNL AudienceManagement] module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Adobe Experience Platform Identity Service] 3.3 or newer. <br><br>The [!UICONTROL Experience Cloud Organization ID] is the ID that a company is provided with upon signing up for the [!UICONTROL Experience Cloud]. Find out your company's Organization ID in [Organizations and Account Linking](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Results: Data Forwarding to [!DNL Audience Manager] {#results-data-forwarding}

Your [!DNL Analytics] implementation sends data to [!DNL Audience Manager] after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* Implemented the [!DNL Adobe Experience Platform Identity Service];
* Followed the implementation steps in this tutorial.

This process sends data to [!DNL Audience Manager]:

* On page view calls;
* From tracked links;
* From video milestone and heartbeat video views.

>[!NOTE]
>
>The variables sent to [!DNL Audience Manager] from [!DNL Analytics] use special prefixes. You need understand and take these prefixes into account when creating [!DNL Audience Manager] traits. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).
