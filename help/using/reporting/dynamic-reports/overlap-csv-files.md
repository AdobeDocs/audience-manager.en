---
description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-title: CSV Files for Overlap Reports
solution: Audience Manager
title: CSV Files for Overlap Reports
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
---

# CSV Files for Overlap Reports{#csv-files-for-overlap-reports}

You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.

## File Name Metadata {#section_F4F001E5849147D0AF4AA3AAAAC56ECE}

The following table list and describes the file naming conventions and file extensions use in an overlap .csv file. In the examples, *italics* indicates a variable placeholder.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metadata Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>File Extension </p> </td> 
   <td colname="col2"> <p>Overlap report files are gzip compressed and have a <span class="codeph"> .gz</span> file extension. You must add the <span class="codeph"> .csv</span> extension to the file after decompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Name </p> </td> 
   <td colname="col2"> <p>File name syntax: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-to-segment files: <span class="codeph">S2S_overlap_<span class="varname"> partner ID</span>_<span class="varname"> yyyy-mm-dd</span>_<span class="varname"> date range</span></span> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-to-trait files: <span class="codeph">S2T_overlap_<span class="varname"> partner ID</span>_<span class="varname"> yyyy-mm-dd</span>_<span class="varname"> date range</span></span> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait files: <span class="codeph">T2T_overlap_<span class="varname"> partner ID</span>_<span class="varname"> yyyy-mm-dd</span>_<span class="varname"> date range</span></span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date Range </p> </td> 
   <td colname="col2"> <p>The date range for a report is a 5-digit ID that includes: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <span class="codeph"> 70000</span> for a 7-day report. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <span class="codeph"> 30000</span> for a 30-day report. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple Files </p> </td> 
   <td colname="col2"> <p>We increment the last digit in the file name if a report contains multiple files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Examples </p> </td> 
   <td colname="col2"> <p>File name examples for a single report: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Single, 7-day file: <span class="codeph"> S2S_overlap_12345_2017_01_14_70000.gz</span> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Single, 30-day file: <span class="codeph"> S2S_overlap_12345_2017_01_14_30000.gz</span> </li> 
     </ul> </p> <p>File name examples for a report with multiple files: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <span class="codeph"> S2S_overlap_12345_2017_01_14_70000.gz</span> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <span class="codeph"> S2S_overlap_12345_2017_01_14_70001.gz</span> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <span class="codeph"> S2S_overlap_12345_2017_01_14_70002.gz</span> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Contents {#section_D2E3E3398CA2494581273D6A950D7172}

In the file, string data is enclosed in double quotes. See the mock data below. This has been truncated for brevity and to fit the screen.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segment-to-Segment Report Records {#section_2D0602508803416E999A36F271AFF2F5}

A data file for your [Segment-to-Segment Overlap Report](segment-segment-overlap-report.md) contains the following records.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_id1</span> </p> </td> 
   <td colname="col2"> <p>The ID of the segment you're comparing to the baseline segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_name1</span> </p> </td> 
   <td colname="col2"> <p>The name of the segment you're comparing to the baseline segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_id2</span> </p> </td> 
   <td colname="col2"> <p>The ID of your baseline segment. The baseline segment is the segment you want to compare with other segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_name2</span> </p> </td> 
   <td colname="col2"> <p>The name of the baseline segment you're comparing to other segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rangeid</span> </p> </td> 
   <td colname="col2"> <p>You can get reports for 7- and 30-day look-back intervals. The <span class="codeph"> rangeid</span> corresponds to the time intervals shown below. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <span class="codeph"> 7</span>: 7-days </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <span class="codeph"> 30</span>: 30-days </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> datethru</span> </p> </td> 
   <td colname="col2"> <p>The processing date for a report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_uniques1</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users in the segment you're comparing to the baseline segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_uniques2</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users in the baseline segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_uniques</span> </p> </td> 
   <td colname="col2"> <p>A total count of the overlap of unique users between the baseline segment and the other segments selected for comparison. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Overlap_perc</span> </p> </td> 
   <td colname="col2"> <p>The % overlap of unique users between the baseline segment and the other segments selected for comparison. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment-to-Trait Report Records {#section_D8D7E1BD977C41D184B277A394B950EA}

A data file for your [Segment-to-Trait Overlap Report](segment-trait-overlap-report.md) contains the following records.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> trait_id</span> </p> </td> 
   <td colname="col2"> <p>Trait ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> trait_name</span> </p> </td> 
   <td colname="col2"> <p>Trait name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dataprovider_type</span> </p> </td> 
   <td colname="col2"> <p>The data provider ID. IDs include: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <span class="codeph"> 1st Party</span> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <span class="codeph"> 3rd Party</span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dataprovider</span> </p> </td> 
   <td colname="col2"> <p>Name of the data provider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rangeid</span> </p> </td> 
   <td colname="col2"> <p>You can get reports for 7- and 30-day look-back intervals. The <span class="codeph"> rangeid</span> corresponds to the time intervals shown below. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <span class="codeph"> 7</span>: 7-days </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <span class="codeph"> 30</span>: 30-days </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> datethru</span> </p> </td> 
   <td colname="col2"> <p>The processing date for a report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users in the selected segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> trait_uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users in a trait. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users shared between the selected segments and traits. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> trait_uniques_overlap_perc</span> </p> </td> 
   <td colname="col2"> <p>% of unique users that overlap between the trait and segment. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> segment_uniques_overlap_perc</span> </p> </td> 
   <td colname="col2"> <p>% of uniques users that overlap between the segment and trait. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait Report Records {#section_850319D1EAC34410B958E967C38FF72E}

A data file for your [Trait-to-Trait Overlap Report](trait-trait-overlap-report.md) contains the following records.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_trait_id</span> </p> </td> 
   <td colname="col2"> <p>The ID of the trait you're comparing to the baseline trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_trait_name</span> </p> </td> 
   <td colname="col2"> <p>The name of the trait you're comparing to the baseline trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> base_trait_id</span> </p> </td> 
   <td colname="col2"> <p>The ID of your baseline trait. The baseline trait is the trait you want to compare with other traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> base_trait_name</span> </p> </td> 
   <td colname="col2"> <p>The name of the baseline trait you're comparing to other traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dataprovider_type</span> </p> </td> 
   <td colname="col2"> <p>The data provider ID. IDs include: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <span class="codeph"> 1st Party</span> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <span class="codeph"> 3rd Party</span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dataprovider</span> </p> </td> 
   <td colname="col2"> <p>Name of the data provider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rangeid</span> </p> </td> 
   <td colname="col2"> <p>You can get reports for 7- and 30-day look-back intervals. The <span class="codeph"> rangeid</span> corresponds to the time intervals shown below. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <span class="codeph"> 7</span>: 7-days </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <span class="codeph"> 30</span>: 30-days </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> datethru</span> </p> </td> 
   <td colname="col2"> <p>The processing date for a report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_trait_uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users shared between the selected traits. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> base_trait_uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users in a base trait. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_uniques</span> </p> </td> 
   <td colname="col2"> <p>The number of unique users shared between the selected traits. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> overlap_trait_uniques_overlap_perc</span> </p> </td> 
   <td colname="col2"> <p>% of unique users that overlap between the selected traits. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> base_trait_uniques_overlap_perc</span> </p> </td> 
   <td colname="col2"> <p>% of uniques users that overlap between the selected traits. In the UI report, this number appears in the pop up window when you hover over a trait in the heatmap results. </p> </td> 
  </tr> 
 </tbody> 
</table>
