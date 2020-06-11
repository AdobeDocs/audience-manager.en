---
description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: Report Technology
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
---

# Report Technology{#report-technology}

Describes the underlying software that powers the interactive reports and the data update schedule.

<!-- 

c_report_technology.xml

 -->

## Interactive Reports Use Tableau Technology

[!DNL Audience Manager] uses [Tableau](https://www.tableausoftware.com/) software to display data in the interactive reports. With [!DNL Tableau], the [!UICONTROL Delivery and Overlap] reports use visual cues and symbols that help you:

* Find high and low performance traits.
* Spot traits and segments with low and high unique visitor overlap.
* Use overlap data to build targeted segments.
* Expand reach by identifying related traits with low overlap.

## Data Update Schedule

Report data is updated weekly each Sunday. The update processes data from Saturday (the day before) back to the previous Sunday. 

## Shapes, Colors, and Sizes Used in Interactive Reports {#shapes-colors-sizes}

Most of the interactive reports display results using shapes of different sizes and colors. This display format is designed to help you make sense of the data visually, without having to wade through rows and columns of numbers.

<!-- 

r_legend.xml

 -->

### Report Legend

The following table defines the shapes, sizes, and colors used in the dynamic reports.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Shapes</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Circles indicate your own first-party traits. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Squares indicate third-party traits. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colors</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Red shades indicate <i>low</i> overlap. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Green shades indicate <i>high</i> overlap. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Size</b> </td> 
   <td colname="col2"> Size increases or decreases in direct proportion to reach (the number or % of clicks or unique users in a trait or segment). </td> 
  </tr> 
 </tbody> 
</table>

## Tableau Documentation {#tableau-documentation}

To learn more about the Tableau controls that you can see in our interactive reports, refer to the official documentation for [Tableau Server on Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm.)