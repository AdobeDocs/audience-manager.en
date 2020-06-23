---
description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Profile Merge Rules Overview
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
---

# [!UICONTROL Profile Merge Rules] Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you can control which data sets are used for segmentation and can target users accurately across multiple devices.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

Typically, audience segmentation and targeting relies on data collected from all users on a device. Data collection and targeting based on device-level data has some disadvantages. For example, you cannot distinguish between multiple users who share a device or accurately target users across multiple devices. Device-centered data collection is no longer sufficient for digital marketing campaigns or cross-device targeting.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] fundamentally changes how [!DNL Audience Manager] collects data and segments users for targeting. It lets you work with 2 distinct types of profiles, a device profile and an [authenticated profile](../../reference/visitor-authentication-states.md).

|Profile Type|Description|
|---|---|
|[!UICONTROL Device Profile]|A [!UICONTROL device profile] is tied to an ID for a given device such as a [!UICONTROL cookie] ID or mobile device ID.<br><br> It includes:<ul><li>[!UICONTROL Rule-based traits] realized when a user is not authenticated.</li><li>[!UICONTROL Onboarded traits] tied to a device ID such as [!UICONTROL cookie-based], third-party data.</li>|
|[!UICONTROL Authenticated Profile]|The [!UICONTROL authenticated profile] is tied to a user ID passed in when a person logs in to your site.<br><br>It includes:<ul><li>[!UICONTROL Rule-based traits] collected across devices when a user is authenticated.</li><li>[!UICONTROL Onboarded traits] in an offline file linked to the same user ID.|

These different profiles control the data you can use for segmentation. For example, with an [authenticated profile](../../reference/visitor-authentication-states.md), you can build accurate [!UICONTROL segments] based on data from multiple devices for a single user. This means you can deliver a consistent brand experience to customers across multiple devices. [!DNL Audience Manager] achieves this by storing the mapping of the different devices a person uses for their online activities to their [authenticated profile](../../reference/visitor-authentication-states.md). These mappings are called the [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Advantages {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* Target users based on [authenticated profile](../../reference/visitor-authentication-states.md), anonymous profiles, or combinations of both.
* Target a specific customer across their devices.
* Build a device graph based on deterministic data.
* Fine tune the data in your [!UICONTROL segments] based on different profiles.
* Gain additional insight into your audience.
