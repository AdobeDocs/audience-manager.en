---
description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Bulk Requests
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
TQID: https://experienceleague.adobe.com/9VACsTAdf5nqwXAeQCqA7ME7M1sTOwt-eW-fyVdE-Ag
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
    internal-label: Reporting
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
    internal-label: Overlap Reports
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Bulk Requests{#bulk-requests}

A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.

>[!IMPORTANT]
>
>The Bulk Management Tools are not an officially supported Adobe offering. Troubleshooting and support through Customer Care will be handled on a case by case basis.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

The [!UICONTROL Request] worksheet does not have its own set of column headers and you don't need to copy IDs to any of the columns. Instead, it returns data based on the action button you click in the toolbar. And, an optional reporting feature returns a frequency count for pixel fires and unique user count for several fixed time intervals.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and: 

1. Click the **[!UICONTROL Request]** tab.
2. In the tool bar at the top of the worksheet, click a request button corresponding to the data you want to work with. You can request:

    * Algorithmic models
    * Data sources
    * Derived signals 
    * Destination mappings 
    * Algorithmic, rule-based, and on-boarded traits 
    * Segments 
    * Trait and segment folder IDs

   The [!DNL Audience Manager] API writes bulk data back to the [!UICONTROL Request] worksheet. 

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. The underlying date/time stamps are recorded in UNIX UTC time. Currently, the worksheet cannot return date/time stamps in a readable format.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
