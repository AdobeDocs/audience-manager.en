---
description: Common product and function-related questions and issues.
keywords: audience manager cookies
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Product Features and Functions FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
index: y
internal: n
snippet: y
---

# Product Features and Functions FAQ{#product-features-and-functions-faq}

Common product and function-related questions and issues.

<!-- 

faq_features_functions.xml

 -->

**What is my Organization ID and how do I find it?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg]. For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`. The *`Organization ID`* is used by Audience Manager's [DIL](../c-dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

**Can I create traits or destinations in bulk?**

Yes. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] tools *are not* supported by [!DNL Audience Manager]. They're provided for convenience and as a courtesy only. For bulk changes, we recommend you work with the [Audience Manager APIs](../c-api/c-api.md#concept_8C41AAD825A24A01806E64C32F71472A) instead.

**Can [!DNL Audience Manager] reduce the need for third-party tags or pixels and improve page load times?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. This eliminates the need to make multiple pixels call from every page. Reducing pixel calls can improve page load times.

**I've subscribed to a data feed. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

**What is [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

**Is there any difference between Adobe Analytics and Audience Manager segments?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences. 
