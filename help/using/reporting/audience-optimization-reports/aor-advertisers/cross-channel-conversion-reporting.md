---
description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Cross Channel Conversion
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
---

# Cross Channel Conversion{#cross-channel-conversion}

The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.

The [!UICONTROL Cross Channel Conversion] reports combine results from the [!DNL Google Campaign Manager] platform with [!DNL Audience Manager] conversion traits. This lets you link offline conversions to online impressions or clicks. 

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM + Ad Server Name]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Consideration </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Minimum number of conversion traits </p> </td> 
   <td colname="col1"> <p>At least one conversion trait must be assigned to a data source in order for the <span class="wintitle"> Cross Channel Conversion</span> reports to run. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Attribution window </p> </td> 
   <td> <p> <b><span class="uicontrol"> The AAM+Google Campaign Manager</span></b> attribution window is 14 days, meaning that only conversion traits exhibited in the last two weeks are considered. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Last-touch methodology </p> </td> 
   <td> <p>The creative that the user has seen last before converting is the one awarded the conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clicks versus impressions </p> </td> 
   <td> <p>A click takes precedence over an impression when deciding attribution if they occur at the exact same time. For example, on a page where multiple creatives are displayed, the one being clicked on is awarded the conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Data recency </p> </td> 
   <td> <p>The reports are always calculated for data available the previous day. </p> </td> 
  </tr> 
 </tbody> 
</table>
