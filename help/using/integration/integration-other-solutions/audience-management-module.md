---
description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implement the Audience Management Module
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
---

# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## Prerequisites {#section_06C407634FCA45079D12E7C6CFA13169}

In addition to implementing the code described in this document, you must also:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implementation {#section_36DFAE407B1D49E5A21079BF2C6C3627}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>The `audienceManagement.setup` function shares parameters with the Audience Manager `DIL.create` function, which you can configure in this code. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#reference_F87131F6C1CC4ECCA064B24B91710FD4).

## Code Elements Defined {#section_C96852A88A0E449090E83A0D65E8129C}

The following table defines important variables in the code sample.

| Parameter | Description |
|--- |--- |
|`partner`|Required. This is a partner name assigned to you by Adobe. It is sometimes referred to as your "partner ID" or "partner subdomain."  Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don't know your partner name.|
|`containerNSID`|Required. Most customers can just set  `"containerNSID":0` . However, if your company needs to customize ID syncs with a different container, you can specify that container ID here.|
|`uuidCookie`|Optional. This configuration lets you set an Adobe  cookie in the first-party domain. This cookie contains the [UUID](../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8) .|
| `visitorService` - `namespace`| Required. The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>&nbsp;The [!UICONTROL Experience Cloud Organization ID] is the ID that a company is provided with upon signing up for the [!UICONTROL Experience Cloud]. Find out your company's Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#section_5878A0C32F844C9DB9C2D009CB717708}

Your [!DNL Analytics] implementation sends data to Audience Manager after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* Implemented the ID service;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* On page view calls;
* From tracked links;
* From video milestone and heartbeat video views.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. You need understand and take these prefixes into account when creating Audience Manager traits. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC).