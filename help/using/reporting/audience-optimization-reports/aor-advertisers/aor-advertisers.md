---
description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization for Advertisers
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
TQID: https://experienceleague.adobe.com/U9Rg-4rwjGdqYsjGDlctn0PBuxAlDjwIBtorAnGtqHU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# [!UICONTROL Audience Optimization] for Advertisers{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager [!UICONTROL segment] metrics to inform segment-centric optimizations and an effective channel mix.

## Data Ingestion Methods {#data-ingestion-methods}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. Sometimes, customers send data by both methods. This helps ensure your reports contain the most comprehensive and accurate information about a visitor. To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentation. You can send data via the following methods listed below.

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) and [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md). 

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

The type of reports you can view depend on the [!UICONTROL RBAC] group you're assigned to. See [Administration](../../../features/administration/administration-overview.md) and [Create a Group](../../../features/administration/administration-overview.md#create-group) for more information.

[!UICONTROL RBAC] groups must have some data sources set up in order to view the [!UICONTROL Audience Optimization] reports. Your [!DNL Audience Manager] consultant will set up these [!UICONTROL data sources] for you. The more [!UICONTROL data sources] in each [!UICONTROL RBAC] user group, the more data those group members will have access to. At a minimum, your consultant will set up at least one of these [!UICONTROL data sources]:

* Advertiser [!UICONTROL data source ]
* Brand [!UICONTROL data source] 
* Platform [!UICONTROL data source]

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group's view. The displayed data will update to respect the selected group. If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the [!UICONTROL data sources] (conversion groups).

## Conversion Groups {#conversion-groups}

In the [!UICONTROL Audience Optimization] reports, **[!UICONTROL Conversion Groups]** are synonymous with [!UICONTROL data sources] that contain at least one conversion trait. [!UICONTROL Data sources] which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) report.
