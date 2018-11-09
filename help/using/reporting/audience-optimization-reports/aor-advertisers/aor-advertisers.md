---
description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization for Advertisers
uuid: 27aaf2eb-f4d1-4959-8bcb-40824b35e38e
index: y
internal: n
snippet: y
---

# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.

## Data Ingestion Methods {#section_964E9959EECF45439820169C74D035A5}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. Sometimes, customers send data by both methods. This helps ensure your reports contain the most comprehensive and accurate information about a visitor. To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#concept_548097F263114FC1811B1EEA21D9C461) documentation. You can send data via the following methods listed below.

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../c-integration/media-data-integration/click-data-pixels.md#concept_E487584D9DBF4D7A8A16B745DAD818CD) and [Capturing Campaign Impression Data via Pixel Calls](../../../c-integration/media-data-integration/impression-data-pixels.md#concept_83852AB68E344D4F8933665C895322C2). 

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#concept_76D2C04AA9904203BDC74E4D38D86C89) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md#concept_CD250EF8D3744CC4A722422970886D87).

## Role-Based Access Controls (RBAC) {#section_D32406E3F55D486985C592B4842CF1AA}

The type of reports you can view depend on the [!UICONTROL RBAC] group you're assigned to. See [Administration](../../../c-features/c-administration/c-administration.md#concept_A606A162611E4256BB80F60715282296) and [Create a Group](../../../c-features/c-administration/administration-overview.md#task_3327F7C4A9834F1BA5007EDA279D40F2) for more information.

[!UICONTROL RBAC] groups must have some data sources set up in order to view the [!UICONTROL Audience Optimization] reports. Your [!DNL Audience Manager] consultant will set up these data sources for you. The more data sources in each [!UICONTROL RBAC] user group, the more data those group members will have access to. At a minimum, your consultant will set up at least one of these data sources:

* Advertiser data source 
* Brand data source 
* Platform data source

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group's view. The displayed data will update to respect the selected group. If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the data sources (conversion groups).

## Conversion Groups {#section_50F6ED5228174DE2865F179725D3F4B0}

In the [!UICONTROL Audience Optimization] reports, **[!UICONTROL Conversion Groups]** are synonymous with data sources that contain at least one conversion trait. Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md#concept_DE9862A845AD426B9C37B11683BD8E6D) report. 
