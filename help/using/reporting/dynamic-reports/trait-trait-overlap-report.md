---
description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Trait-to-Trait Overlap Report
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
index: y
internal: n
snippet: y
---

# Trait-to-Trait Overlap Report{#trait-to-trait-overlap-report}

Returns data on the number of unique users shared among all your first and third-party traits.

<!-- 

c_overlap_reports.xml

 -->

## Overview

The [!UICONTROL Trait-to-Trait Overlap] report returns data on the % of unique users shared between all your own traits and your third-party traits. As an optimization tool, this report helps you:

* Create segments with high or low overlap, depending on your needs. Traits with high overlap give you a targeted audience, but fewer unique visitors. Traits with low overlap can be useful to reach a larger, unique visitor set. 
* Validate third-party trait data: Strong overlap between similar first and third-party traits suggests that the trait from your data partner is accurate and trustworthy. Conversely, low overlap can indicate that a third-party trait may not actually contain the same information as your own, similar first-party trait. 
* Find unexpected overlap between traits and use that information to build innovative segments.

## Sample Report

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report. 

>[!NOTE]
>
>The [!UICONTROL Trait-to-Trait Overlap] report returns an empty field when it compares the same trait to itself.

![](assets/t2t_overlap90.png)

## Drill Down on Individual Data Points

Select an individual point to view data details in a pop up window. Your click actions automatically update data displayed in the report. 

## Trait-to-Trait Overlap Data Pop Fields Defined {#reference_620049DEC6B04BF999DE6C11B3E7649A}

Describes the metrics displayed in the popup window when you click an individual data point.

<!-- 

r_t2t_data_pop.xml

 -->

The popup for the [!UICONTROL Trait-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.  

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Data Provider Name</span></b> </td> 
   <td colname="col2"> Name of the trait's owner. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Data Provider Type</span></b> </td> 
   <td colname="col2">Defines the type of provider a trait belongs to. Can be either: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">First-party (your own trait). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Third-party (from an outside data partner/vendor). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait ID</span></b> </td> 
   <td colname="col2"> Unique numeric ID for that trait. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Name</span></b> </td> 
   <td colname="col2"> Name of the trait. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlap %</span></b> </td> 
   <td colname="col2"> Shows the % of unique overlap between compared traits (overlap uniques/trait uniques). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlap Uniques</span></b> </td> 
   <td colname="col2"> The number of unique visitors shared between the compared traits. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques</span></b> </td> 
   <td colname="col2"> The number of unique visitors in the trait. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Filter Report Results With the Data Sliders](../../reporting/dynamic-reports/data-sliders.md#concept_00E60A0BDB274B07A1DD342EE5554C37)
>* [Shapes, Colors, and Sizes Used in Dynamic Reports](../../reporting/dynamic-reports/interactive-report-technology.md#reference_25F1411379B34946B5AB8156A0F87626)
>* [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#reference_8D90E6C1F0AE46D4AC0911707395BED6)
>* [Overlap Reports: Update Schedule and Minimum Segment Size](../../reporting/dynamic-reports/overlap-minimum-segment-size.md#concept_6C439B845E684C40A726C546F9AF0AFD)
>* [Data Sampling and Error Rates in Selected Audience Manager Reports...](../../reporting/report-sampling.md#concept_624BB1069F8A4CBD948ABD87105329E4)
>* [CSV Files for Overlap Reports](../../reporting/dynamic-reports/overlap-csv-files.md#concept_440C76BFFAC74669972CE538F8B5040F)