---
description: Follow these instructions to generate a full synchronization file that includes recently active users only. You may want to filter for active users to push relevant data to an on-site targeting system or to limit the size of the files sent to a DSP. You cannot use this filter with incremental synchronization.
seo-description: Follow these instructions to generate a full synchronization file that includes recently active users only. You may want to filter for active users to push relevant data to an on-site targeting system or to limit the size of the files sent to a DSP. You cannot use this filter with incremental synchronization.
seo-title: Filter Outbound Data by Active Users Only
title: Filter Outbound Data by Active Users Only
uuid: a2b4a385-eee3-458c-b978-09509cacb397
---

# Filter Outbound Data by Active Users Only{#filter-outbound-data-by-active-users-only}

Follow these instructions to generate a full synchronization file that includes recently active users only. You may want to filter for active users to push relevant data to an on-site targeting system or to limit the size of the files sent to a DSP. You cannot use this filter with incremental synchronization.

>[!NOTE]
>
>A visitor does not need to be seen on a selected customer site or in their ad traffic to qualify as "active." They can be seen by any [!DNL Audience Manager] customer or partner to qualify as "active."

To filter by active users only: 

1. Click **[!UICONTROL Companies]**.
1. Select the company you want to work with and click **[!UICONTROL Destinations]**.
1. In the [!UICONTROL Batch Data] section, set the following options:

    * **[!UICONTROL Sync Type]**: Select **[!UICONTROL Customer]** or **[!UICONTROL Platform]**. 
    
    * **[!UICONTROL Sync Type Lookback Period]**: This time interval defines the range of your data file. Choices include **[!UICONTROL 24 hours]**, **[!UICONTROL 7 days]**, **[!UICONTROL 30 days]**. 
    
    * **[!UICONTROL Incremental Sync Scheduled Run]**: Select **[!UICONTROL Never]**. Remember, this filter applies to full synchronization files only. 
    
    * **[!UICONTROL Full Sync Scheduled Run]**: This determines how often you want to receive this file. Choices include **[!UICONTROL 24 hours]**, **[!UICONTROL 7 days]**, **[!UICONTROL 30 days]**, or **[!UICONTROL Never]** (to disable).

1. Click **[!UICONTROL Save]**.
