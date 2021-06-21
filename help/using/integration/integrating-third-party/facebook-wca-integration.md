---
description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA Integration
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
---
# [!DNL Facebook WCA] Integration {#facebook-wca-integration}

This page illustrates the process of creating [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels for the purposes of sending web-based [!DNL Audience Manager] audience segments to [!DNL Facebook], for online ad targeting with improved transparency.

## Overview {#overview}

[Facebook Website Custom Audiences (WCA)](https://www.facebook.com/business/help/449542958510885) allows you to create a list of people who have visited certain pages or taken particular actions on your website. [!DNL Audience Manager] enables activation in [!DNL WCA] using [!DNL URL] destinations, with which you can configure a custom pixel-based integration to send web-based audiences to [!DNL Facebook] for targeting.

![Facebook WCA Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the [!UICONTROL Website] audience for social platforms option in [URL destinations](/help/using/features/destinations/create-url-destination.md). Social platforms require that referrer information be unmasked when sent to their platform. Please be aware that this means that the destination platform/partner will be able to see information in your referrer [!DNL URL].

## Prerequisites {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segments, ready to assign to your new [!DNL Facebook] destination. Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the [!DNL Audience Manager] UI.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 or newer. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) to import data into [!DNL Audience Manager], you must use AppMeasurement version 2.12 or newer. Download [!DNL AppMeasurement] using the [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html).

## Step 1 - Create a [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Create a new [!UICONTROL URL Destination] in [!DNL Audience Manager] and name it [!DNL Facebook Website Custom Audiences]. Use the settings below when creating the destination. You can also refer to the [Configure a URL Destination](/help/using/features/destinations/create-url-destination.md) page.

### Basic Information

* **[!UICONTROL Category]**: Custom
* **[!UICONTROL Type]**: [!DNL URL]
* Select the **[!UICONTROL Auto-fill Destination Mapping]** check box, then select **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Select the option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> This export label prevents third party data and data derived from device graphs from being included in the segments.

### Configuration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. By selecting this [!UICONTROL URL Type] option, [!DNL Audience Manager] does not obscure the referrer [!DNL URL] information when firing a [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* In the **[!UICONTROL Base URL]** and **[!UICONTROL Secure URL]** field, enter the [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Example pixel fired from the page. This example shows a user who qualifies for three [!DNL Audience Manager] segments, with the IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

|Parameter | Description |
|---------|----------|
| `id` | Your [!DNL Facebook] pixel ID, which you can find in the [!DNL Facebook Ad Manager] user interface when creating audience pixels. |
| `ev` | Event. This is an arbitrary value, which will appear in the [!DNL Facebook Ad Manager] user interface once the pixel begins to fire on site. See the [!UICONTROL Include] item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | An additional parameter, which will begin to populate within the [!DNL Facebook Ad Manager] user interface once the pixel begins to fire on site. `segID` is also arbitrary. |
| `%ALIAS%` | An [!DNL Audience Manager] macro, which will be dynamically replaced with the [!DNL Audience Manager] [!UICONTROL segment] IDs that the site visitor qualifies for, delimited by comma , |

Your [!UICONTROL URL destination] configuration should look like in the image below:

![Destintion Configuration](/help/using/integration/assets/facebook-wca.png)

Save the [!UICONTROL destination]. Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/create-url-destination.md) workflow, map the applicable segment to your newly created [!UICONTROL destination]. Notice the mapping value is auto-populated with the [!DNL Audience Manager] [!UICONTROL segment ID].

Enter an end date if applicable, otherwise leave blank for no end date.

## Step 3 - Create an [!UICONTROL Audience] within [!DNL Facebook Ads Manager] {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the [!DNL Facebook] help documentation. Select the [!UICONTROL Create Audience] options in the table below:

|Item | Description |
|---------|----------|
| Website traffic | Custom Combination |
| Include | <ul><li>Select **[!UICONTROL Event]** > Select **[!UICONTROL Adobe-Audience-Manager-Segment]**. This was the value of the `ev` parameter in the example pixel in step 1. Note that if the pixel is yet to fire, the **[!UICONTROL Event]** option or **[!UICONTROL Adobe-Audience-Manager-Segment]** may not appear in the [!DNL Facebook] user interface.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>This is important, considering that visitors may qualify for multiple segments, there may be multiple [!UICONTROL segment IDs] in the pixel parameter. Using the equals (`=`) operator may not qualify your visitors for the audience, and you will observe a lower volume.</p></li><li>Add a value: Enter the [!DNL Audience Manager] segment ID.</li></ul> |
| Add New Condition | Optional setting. |
| In the Last | Optional setting. |
| Audience Name | We recommend you use the same [!DNL Audience Manager] segment name for consistency, unless you are adding additional conditions to this Audience. |

## Step 4 - Assign the [!UICONTROL Audience] to a [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

After creating the [!DNL Custom Audience], assign it to an ad campaign. Create a new campaign or edit an existing one and you will find your newly created audience is listed in the [!DNL Facebook] user interface. Your ad campaign will target users who have seen the pixel fire on their browser when visiting your site, if [!DNL Audience Manager] includes them in the segment.

## Summary {#summary}

Now that you have assigned your [!DNL Audience Manager] segment to the [!DNL Facebook WCA] destination, [!DNL Audience Manager] will selectively fire the [!DNL Facebook WCA] pixel to users of a given segment with the respective segment ID in the pixel to populate the [!DNL Facebook Audience]. This results in a gradual increase in the [!DNL Facebook Audience] the more the tag is fired to the applicable audience on your site.

>[!NOTE]
>
> If a user falls out of the [!DNL Audience Manager] segment, there is currently no way for [!DNL Audience Manager] to inform [!DNL Facebook] to remove the user from the [!DNL Custom Audience].
>
