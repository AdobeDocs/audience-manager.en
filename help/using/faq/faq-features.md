---
description: Common product and function-related questions and issues.
keywords: audience manager cookies
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Product Features and Functions FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
TQID: https://experienceleague.adobe.com/gsJ4qXlNDpfWmTq0jjmtjfUWI60yRr7uBTxZjsF-pQE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
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

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

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

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Tags]. For more information, see [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

&nbsp;

**Is there any difference between Adobe Analytics and Audience Manager segments?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.
