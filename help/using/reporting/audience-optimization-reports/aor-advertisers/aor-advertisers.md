---
description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization for Advertisers
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
---

# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.

## Data Ingestion Methods {#data-ingestion-methods}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. Sometimes, customers send data by both methods. This helps ensure your reports contain the most comprehensive and accurate information about a visitor. To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentation. You can send data via the following methods listed below.

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) and [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md). 

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Role-Based Access Controls (RBAC) {#rbac}

The type of reports you can view depend on the [!UICONTROL RBAC] group you're assigned to. See [Administration](../../../features/administration/administration-overview.md) and [Create a Group](../../../features/administration/administration-overview.md#create-group) for more information.

[!UICONTROL RBAC] groups must have some data sources set up in order to view the [!UICONTROL Audience Optimization] reports. Your [!DNL Audience Manager] consultant will set up these data sources for you. The more data sources in each [!UICONTROL RBAC] user group, the more data those group members will have access to. At a minimum, your consultant will set up at least one of these data sources:

* Advertiser data source 
* Brand data source 
* Platform data source

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group's view. The displayed data will update to respect the selected group. If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the data sources (conversion groups).

## Conversion Groups {#conversion-groups}

In the [!UICONTROL Audience Optimization] reports, **[!UICONTROL Conversion Groups]** are synonymous with data sources that contain at least one conversion trait. Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) report. 
