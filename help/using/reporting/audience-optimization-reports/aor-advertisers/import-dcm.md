---
description: Set up a Google group to bring your DoubleClick Campaign Manager (DCM) data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to DCM resources to help you get started.
seo-description: Set up a Google group to bring your DoubleClick Campaign Manager (DCM) data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to DCM resources to help you get started.
seo-title: Import DCM Data Files Into Audience Manager
solution: Audience Manager
title: Import DCM Data Files Into Audience Manager
uuid: f48ccbfd-7174-4f3b-87bb-c89e8946ba1f
index: y
internal: n
snippet: y
translate: y
---

# Import DCM Data Files Into Audience Manager

Set up a Google group to bring your DoubleClick Campaign Manager (DCM) data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to DCM resources to help you get started.



**Integration summary** 


DCM is [!DNL Google]'s replacement for [!DNL DoubleClick for Advertisers] (DFA). Similar to DFA, DCM customers can import, view, and work with their data in [!DNL Audience Manager]. But, [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. To import these files, the burden of effort lies with the customer. However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Also, you can review the steps listed below to get started. 



>[!CAUTION]
>
>DCM data files contain data for all your advertisers or clients. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager]. 



**Data transfer frequency and availability** 


[!DNL Audience Manager] checks for and transfers data once each day. Data is usually available in [!DNL Audience Manager] after 24-hours. 


**Steps** 

1. [Create a group](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

[!DNL Audience Manager]1. [Verify your Google Cloud Storage status](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

[!UICONTROL Data Transfer][!UICONTROL Match Tables]1. [Get a data file URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

[!DNL Google]1. [Set bucket permissions](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

[!DNL Cloud Storage Manager][!UICONTROL Data Transfer][!UICONTROL Match Table]1. [Set up data sharing](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   `PartnerId1``PartnerId2`[!DNL Audience Manager][!DNL Audience Manager][!DNL Audience Manager]1. Invite [!DNL Audience Manager] to join the group.

[!DNL Audience Manager]1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   **Advertiser Analytics: DCM Platform****Advertiser Analytics: AAM+DCM Platform.**[Create Data Sources](../../../c_features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44)**Cookie**1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../c_integration/media-data-integration/actionable-log-files.md#concept_464D49C698A04E26AFD8AA0F640E5EB3) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
