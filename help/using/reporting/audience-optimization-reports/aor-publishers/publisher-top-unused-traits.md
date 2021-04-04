---
description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: Top Unused Traits
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
---
# Top Unused Traits{#top-unused-traits}

Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.

## Use Case {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. This view can point out the best traits to use in an audience segment for either campaign optimization or net new opportunities.

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. Any traits responsible for less or more than the limits you set are not displayed in the report.

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. Note that only the 30-day look-back period is available for this report.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import Google Ad Manager (formerly DFP) Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**Sample Report**

Your [!UICONTROL Top Unused Traits] report could look similar to the one below. In your report, click on a bubble to view the underlying data.

See descriptions for the additional information in the table below the sample report.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Data Provider Type</span> </p> </td> 
   <td colname="col2"> <p>Specifies whether the selected data source contains first party or third party traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait ID</span> </p> </td> 
   <td colname="col2"> <p>The unique ID of this trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Name</span> </p> </td> 
   <td colname="col2"> <p>The alphanumerical name that you or the data provider assigned to this trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Order</span> </p> </td> 
   <td colname="col2"> <p>The web property for which you are seeing this report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>The number of times that members of this trait have been exposed to your inventory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of trait members, within the last 30 days. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

The position of your traits in a report can tell you a lot about which traits you could use to optimize existing audience segments. 

The traits situated higher on the Impressions axis are the ones you want to use in your campaigns. For traits with a low number of impressions, it is unlikely that you're reaching this audience on your web property, based on your [!DNL Google Ad Manager] data. 

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Placement Indicates </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Top Left</b> </p> </td> 
   <td colname="col2"> <p>High number of impressions, low number of trait realizations. </p> <p>This is a highly accurate audience that is not yet member of a segment. Consider for targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bottom Left</b> </p> </td> 
   <td colname="col2"> <p>Low number of impressions, low number of trait realizations. </p> <p> Rule out these traits, as the members are not contributing to impressions on your web properties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Top Right</b> </p> </td> 
   <td colname="col2"> <p>High number of impressions, high number of trait realizations. </p> <p>A high reach against an audience that is not denoted in a segment yet. This audience is a prime candidate for targeting due to the high number of impressions and the scale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bottom Right</b> </p> </td> 
   <td colname="col2"> <p>Low number of impressions, high number of trait realizations. </p> <p> You can rule out these traits, as the members are not contributing to impressions on your web properties. </p> </td> 
  </tr> 
 </tbody> 
</table>
