---
description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from the Adobe Experience Cloud Device Co-op or other third-party device graph sources.
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from the Adobe Experience Cloud Device Co-op or other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: Report Metrics for Profile Merge Rules
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
---

# Report Metrics for [!UICONTROL Profile Merge Rules] {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] metrics provide data about people and devices that authenticate to your site. The data and graphs in [!UICONTROL Profile Link] update dynamically as you create a merge rules or when you click an existing rule from the [!UICONTROL Profile Merge Rules] dashboard. These metrics can include device graph from the [!DNL Adobe Experience Cloud Device Co-op] or other third-party device graph sources.

## Merge Rule Metrics {#section_23F45E4C374241709A246058F4D92A23}

Reports return data in side-by-side bar graphs when your merge rules use data from the [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) or other, third-party device graphs you may have access to in [!DNL Audience Manager]. This lets you compare your authenticated, first-party data with cross-device data provided by the [!UICONTROL Experience Cloud Device Co-op] or another, third-party device graph. For information about data returned by the [!UICONTROL Device Co-op], see [The Device Graph: Internal Processes and Output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). This data is updated daily.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Authenticated Activity</span></b> </p> </td> 
   <td colname="col2"> <p>Shows: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Active People</span>: The number of people who have authenticated to your site for the last 60-days. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Cross Device</span>: The total number of <a href="../../features/profile-merge-rules/merge-rules-start.md#concept_3B7696B3EC77416492D3B99EBD79EA44"> Cross Device IDs</a> stored in the <a href="../../features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44"> Data Source</a> of the selected <a href="../../features/profile-merge-rules/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0"> Authenticated Profile</a> for the lifetime that the data source has existed. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Active People</span>: Shows <span class="wintitle"> Active People</span> as a %. </li> 
    </ul> <p> <span class="wintitle"> Authenticated Activity</span> lets you compare data sources by activity, volume, and percent. It can help you find a data source that has a lot of people and a high percentage of active users. Or, you may find value in comparing data sources with high proportion of active users compared to the total audience size. For example, sometimes a data source with low total lifetime numbers and high activity are more valuable than those with high lifetime results and low activity numbers. </p> <p> <p>Note: The <span class="wintitle"> Authenticated Activity</span> metrics contain <span class="wintitle"> Profile Link</span> data only. This report does not include <span class="wintitle"> Device Graph</span> data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Average Devices per Person</span></b> </p> </td> 
   <td colname="col2"> <p> Shows the average number of devices that are used by visitors who have authenticated to your site for the selected data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total Devices</span></b> </p> </td> 
   <td colname="col2"> <p>Shows the total number of devices people have used to authenticate to your site for the selected data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total People</span></b> </p> </td> 
   <td colname="col2"> <p>Shows the total number of people who have been identified deterministically for the selected data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Device Graph Metrics {#section_E7862CA6AC9D4E04ADA75A235DC29B64}

The [!UICONTROL Merge Rules] reports also show data on the total number of people and devices who have visited your site for the selected data source and device graph. These metrics return data based on pre-set time intervals (the look-back period) that vary depending on the device option you select when creating a rule. The following table lists these report intervals for each of the device graph options.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Device Graph Option </th> 
   <th colname="col2" class="entry"> Report Look-back Interval </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Total People: 60-days </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Total Devices: 120-days </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op Device Graph</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Total People: 180-days </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Total Devices: 180-days </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Total People: 180-days </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Total Devices: 180-days </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Total People: 60-days </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Total Devices 60-days </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Reports {#section_44086DF2594A4A60916A7077851F75BA}

### [!UICONTROL Standard Profile Link] Report

A standard [!UICONTROL Profile Link] report looks like the following example. Merge rules that use multiple data sources (up to 3, maximum) show graphs in separate tabs for each data source. This merge rule does not include [!UICONTROL Device Co-op] data.

![](assets/coop-metrics1.png)

### [!UICONTROL Profile Link] Report With Device Graph Data

A [!UICONTROL Profile Link] report that includes device graph data from the [!UICONTROL Adobe Experience Cloud Device Co-op] or a third-party device graph shows [!UICONTROL Profile Link] and device graph data with side-by-side bar graphs. Placing these graphs adjacent to each other lets you evaluate the benefits of using the [!UICONTROL Experience Cloud Device Co-op] compared to [!UICONTROL Profile Link] by itself. Merge rules that use multiple data sources (up to 3, maximum) show graphs in separate tabs for each data source. As a reminder, the [!UICONTROL Authenticated Activity] graph and metrics do not return data from the [!DNL Adobe] device graph or other, third-party device graphs you may have access to in [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## [!UICONTROL Profile Link] Trend Graphs {#section_5A834A740513416B8A3533AE24357569}

In addition to the other data visualizations, [!UICONTROL Profile Link] reports include a line graph. The line graph is designed to show you trends over time for your profile rules. Trend graphs (and the other reports) are available when you click a rule from the [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). These graphs include device graph data if you're a member of the [!UICONTROL Device Co-op] or other, third-party device graphs you may have access to in [!DNL Audience Manager]. Click on a trend line to see underlying data.

![](assets/authenticated_trends.png)

>[!MORE_LIKE_THIS]
>
>* [Profile Merge Rules FAQ](../../faq/faq-profile-merge.md#concept_C8E29A974E194B62B0BAC1CCDD0DF4FF)
