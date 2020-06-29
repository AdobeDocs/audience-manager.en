---
description: Common product and function-related questions and issues.
keywords: audience manager cookies
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Product Features and Functions FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
---

# Product Features and Functions FAQ{#product-features-and-functions-faq}

Common product and function-related questions and issues.

&nbsp;

<!-- 

faq_features_functions.xml

 -->

**What is my Organization ID and how do I find it?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

&nbsp;

**Can I create traits or destinations in bulk?**

Yes. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] tools *are not* supported by [!DNL Audience Manager]. They're provided for convenience and as a courtesy only. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

&nbsp;

**When performing a bulk ID export to a destination, some of the customer IDs are missing. Why does that happen?**

When a device ID ([AAM UUID](../reference/ids-in-aam.md)) is linked to multiple CRM IDs ([DPUUIDs](../reference/ids-in-aam.md)), only the latest mapping gets exported. This is why you may see a lower than expected number of device IDs being exported.

&nbsp;

**Can [!DNL Audience Manager] reduce the need for third-party tags or pixels and improve page load times?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. This eliminates the need to make multiple pixels call from every page. Reducing pixel calls can improve page load times.

&nbsp;

**I've subscribed to a data feed. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

&nbsp;

**What is [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

&nbsp;

**What are the differences between Algorithmic Models and Trait Recommendations? When should I use each of them?**

**Algorithmic Models**

Algorithmic Models not only finds the most influential traits, but also scores users based on those traits and assigns each user an individual score. You then create algorithmic traits to target your users. With accuracy and reach controls in the Trait Builder, you can specify which users amongst all those who have the influential traits you want to target.

Algorithmic Models enables you to select users at different accuracy levels and test in Audience Lab which group of users converts better. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Algorithmic Models, the model runs every 8 days and refreshes the users qualified for algorithmic traits.

**Trait Recommendations**

Trait Recommendations is a quick way to get insights on other traits which are similar to the ones you are using in a segment.

You should use Trait Recommendations when:

* You need quick insights while building a segment;
* You are using the segments for short campaigns or when you want to quickly suppress audience who converts;
* You are trying to maximize reach.

&nbsp;

**Is there any difference between Adobe Analytics and Audience Manager segments?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.
