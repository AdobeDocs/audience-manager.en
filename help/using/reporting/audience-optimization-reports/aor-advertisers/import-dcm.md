---
description: Set up a Google group to bring your DoubleClick Campaign Manager (DCM) data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to DCM resources to help you get started.
seo-description: Set up a Google group to bring your DoubleClick Campaign Manager (DCM) data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to DCM resources to help you get started.
seo-title: Import DCM Data Files Into Audience Manager
solution: Audience Manager
title: Import DCM Data Files Into Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
---

# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Set up a Google group to bring your DoubleClick Campaign Manager (DCM) data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to DCM resources to help you get started.

## Integration summary

DCM is [!DNL Google]'s replacement for [!DNL DoubleClick for Advertisers] (DFA). Similar to DFA, DCM customers can import, view, and work with their data in [!DNL Audience Manager]. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. To import these files, the burden of effort lies with the customer. 

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Also, you can review the steps listed below to get started.

>[!CAUTION]
>
>DCM data files contain data for all your advertisers or clients. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## Data transfer frequency and availability

[!DNL Audience Manager] checks for and transfers data once each day. Data is usually available in [!DNL Audience Manager] after 24-hours.

## Steps

1. [Create a group](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Groups control access to your DCM data. Eventually, you'll invite and add [!DNL Audience Manager] to this group. 
   
1. [Verify your Google Cloud Storage status](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. You'll need to setup a bucket or make sure your new group has access to an existing data storage bucket. 

1. [Get a data file URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Work with your DCM Account Manager or Platform Solutions Consultant. They will provide you with a URL to your data files. [!DNL Google] might change the format for bucket and file names in future releases. Again, work with your DCM Account Manager to make sure you're using the right formats. 
   
1. [Set bucket permissions](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. 
   
1. [Set up data sharing](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Shared DCM user IDs are encrypted to protect privacy. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. These columns contain encoded user IDs specific to each company that receives these files. 
   
   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. This means we can match and synchronize users with confidence and accuracy. 
   
   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you're already sharing data with 2 other third-party partners. 

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. Send an invitation email to DFA-AAM@adobe.com. Be sure to include the data file URL from step 3. Our internal teams will work with you to verify access after accepting the invitation. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44) workflow, set the ID type to `Cookie`. Share the IDs of the two new data sources with our internal teams. 
   
1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md#concept_464D49C698A04E26AFD8AA0F640E5EB3) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
