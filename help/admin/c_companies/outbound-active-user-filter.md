---
description: Follow these instructions to generate a full synchronization file that includes recently active users only. You may want to filter for active users to push relevant data to an on-site targeting system or to limit the size of the files sent to a DSP. You cannot use this filter with incremental synchronization.
seo-description: Follow these instructions to generate a full synchronization file that includes recently active users only. You may want to filter for active users to push relevant data to an on-site targeting system or to limit the size of the files sent to a DSP. You cannot use this filter with incremental synchronization.
seo-title: Filter Outbound Data by Active Users Only
title: Filter Outbound Data by Active Users Only
uuid: d5d66bad-aa48-4e50-854e-abc6ddcaa788
index: y
internal: n
snippet: y
translate: y
---

# Filter Outbound Data by Active Users Only


>[!NOTE]
>
>A visitor does not need to be seen on a selected customer site or in their ad traffic to qualify as "active." They can be seen by any [!DNL  Audience Manager] customer or partner to qualify as "active." 



To filter by active users only: 

>1. Click **[!UICONTROL  Companies]**.
>1. Select the company you want to work with and click **[!UICONTROL  Destinations]**.
>1. In the [!UICONTROL  Batch Data] section, set the following options:
>    * **[!UICONTROL  Sync Type]**: Select **[!UICONTROL  Customer]** or **[!UICONTROL  Platform]**.
>    * **[!UICONTROL  Sync Type Lookback Period]**: This time interval defines the range of your data file. Choices include 24-hours, 7-days, 30-days.
>    * **[!UICONTROL  Incremental Sync Scheduled Run]**: Select **[!UICONTROL  Never]**. Remember, this filter applies to full synchronization files only.
>    * **[!UICONTROL  Full Sync Scheduled Run]**: This determines how often you want to receive this file. Choices include 24-hours, 7-days, 30-days, or Never (to disable).
>1. Click **[!UICONTROL  Save]**.
