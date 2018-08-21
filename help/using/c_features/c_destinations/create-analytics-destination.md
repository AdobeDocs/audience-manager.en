---
description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configure an Analytics Destination
uuid: 05359df2-87a1-48ed-998b-181a2c7152ed
index: y
internal: n
snippet: y
translate: y
---

# Configure an Analytics Destination


## Requirements {#section_D6D1A27A528B4FB698F9F698DF982430}

See [ Audience Analytics ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/). 

## Your Default Analytics Destination and New Analytics Destinations {#section_4CF105723B6A447B9DC214A009D522DF}



<table id="table_5085EDB0CFA04AB6A1C6633C20113ABC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Analytics Destination Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Default</b> </p> </td> 
   <td colname="col2"> <p>The name of this default destination is "Adobe Analytics," which you can edit. Mapped report suite IDs appear in folder storage for your Audience Manager traits and segments. </p> <p>Audience Manager creates one destination automatically if your account has: </p> <p> 
     <ul id="ul_35019C7BFA3148818DCF030A389E7354"> 
      <li id="li_A9EA537C7DCA4A578BC4A44CFFA0FFB5">Met the requirements described in the <a href="https://marketing.adobe.com/resources/help/en_US/analytics/audiences/" format="https" scope="external"> Audience Analytics </a> documentation. </li> 
      <li id="li_F87D2FAA998141679F96FFE736C1D569">A <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html" format="https" scope="external"> report suite </a> in Analytics. </li> 
      <li id="li_5638FB572C2D44108F2F2C0D48B3DA5C"> <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="https" scope="external"> Mapped a report suite to an organization </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>New</b> </p> </td> 
   <td colname="col2"> <p>To create new <span class="keyword"> Analytics </span> destinations, go to <span class="uicontrol"> Audience Data &amp;gt; Destinations &amp;gt; Create New Destination </span> and follow the steps for each section described below. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Step 1: Provide Basic Information {#section_A7F8DC1488EE4583BAD74999A54A13AC}

This section contains fields and options that start the [!DNL  Analytics] destination creation process. To complete this section: 


1. Click **[!UICONTROL  Basic Information]** to expose the controls.
1. Name the destination. Avoid abbreviations and special characters.
1. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
1. *(Optional)* In the **[!UICONTROL  Platform]** list, leave the default set to **[!UICONTROL  All]**. Currently, these options don't do anything. They're designed to support features that may be added at a later date.
1. In the **[!UICONTROL  Category]** list, select **[!UICONTROL  Adobe Experience Cloud]**.
1. In the **[!UICONTROL  Type]** list, select **[!UICONTROL  Adobe Analytics]**.
1. Click **[!UICONTROL  Save]** to go to the Configuration settings or click **[!UICONTROL  Data Export Labels]** to apply export controls to the destination.



>[!NOTE]
>
>For an Analytics destination, the **[!UICONTROL  Auto-fill Destination Mappping]** check box and **[!UICONTROL  Segment ID]** option are selected by default. You cannot change these settings. 



![](assets/basicinformation.png) 

## Step 2: Configure Data Export Controls {#section_534544B5845C4647B7867FC4DE951F83}

This section contains options that apply [ Data Export Controls ](../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C) to an [!DNL  Analytics] destination. Skip this step if you do not use data export controls. To complete this section: 


1. Click **[!UICONTROL  Data Export Controls]** to expose the controls.
1. Select a label that corresponds to the data export control applied to the destination (see [ Add Data Export Labels to a Destination ](../../c_features/c_destinations/t_export_labels.md#task_A4BA30472E6F4687AC3F1B33F51909D9) ). For [!DNL  Analytics] destinations, the PII check box is selected by default.
1. Click **[!UICONTROL  Save]**.


![](assets/exportControls.png) 

## Step 3: Map Report Suites {#section_854920868BFC47F789F2435004F13A04}

The Configuration section lists your Analytics Report Suites that have been enabled for server-side forwarding. If you have multiple Analytics destinations, the report suites assigned to these destinations will be mutually exclusive and enforced by Audience Manager. 

To complete this section: 


1. Click **[!UICONTROL  Configuration]** to expose the controls.
1. Select one (or more) report suites that you want to send segments to.
1. Click **[!UICONTROL  Save]**.


![](assets/reportSuites.png) 

## Step 4: Segment Mappings {#section_98C5681D46D147CD812993DCAD5CBE16}

This section provides options that let you map segments automatically or manually. 



<table id="table_E23E6D6DC51A474EAADA0DF5489EA3FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mapping Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Automatically map all current and future segments </span> </p> </td> 
   <td colname="col2"> <p>Selected by default, this feature sends all segments that a visitor qualifies for, on a per-hit basis, to <span class="keyword"> Analytics </span>. </p> <p>If a visitor belongs to more than 150 <span class="keyword"> Audience Manager </span> segments on a single hit, only the 150-most recently qualified segments are sent to Analytics, while the remaining list is truncated. An additional flag is sent to Analytics signifying that the segment list was truncated. This action displays as “Audience limit reached” in the Audiences Name dimension and “1” in the Audiences ID dimension. See the <a href="https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html" format="https" scope="external"> FAQ </a> for details. </p> <p>Also, this option affects destination availability in <a href="../../c_features/c_segments/c_segment_builder/c_segment_builder.md#concept_FABA1F399CFD4E83B874043638D0FA54" format="dita" scope="local"> Segment Builder </a>. For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the <a href="../../c_features/c_segments/c_segment_builder/r_segment_destinations_map/r_segment_destinations_map.md#reference_D4D92F9F114449C9BC2A51A1C746D92F" format="dita" scope="local"> destination mappings </a> section of Segment Builder. The Analytics destination appears grayed-out and shows "Analytics" in the Type column of the Destination browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Manually map segments </span> </p> </td> 
   <td colname="col2"> <p>This option exposes search and browse controls that let you choose which segments you want to send to <span class="keyword"> Analytics </span>. </p> <p>To search for a segment: </p> 
    <ol id="ol_043CCCE3390A4316A4274D1A126E1EA2"> 
     <li id="li_65F1F2778EC7496D871DFFA8AF9A0655">Type the segment name or ID in the search field. </li> 
     <li id="li_F99680DA004942C09ED19D230BFA2D73">Click <span class="uicontrol"> Add </span>. </li> 
     <li id="li_66998133618740F8A194641C61B0B88F">Continue to search and add segments or click <span class="uicontrol"> Done </span>. </li> 
    </ol> <p>To browse for a segment: </p> 
    <ol id="ol_ADA1720626B94814B18D01606876CC72"> 
     <li id="li_6363D0CD83C94424B2DA9E48CFC6E6FA">Click <span class="uicontrol"> Browse all segments </span>. This exposes a list of available segments. </li> 
     <li id="li_39059DA5008B4406BAC03D4EF51C664E">From the list, select the check box of the segment you want to use and click <span class="uicontrol"> Add selected segments </span>. </li> 
     <li id="li_613EF0BDE2E347AFBD827393648A088D">Click <span class="uicontrol"> Save </span> in the <span class="wintitle"> Add Mappings </span> window. You can't change the mappings, start, or end dates during the beta release. </li> 
     <li id="li_AAC29967B272421689D1B33744D5F46E">Continue to browse and add segments or click <span class="uicontrol"> Done </span>. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/mapSegments.png) 

## Next Steps {#section_8C768C6F5B334036890006F29BF6F29C}

After you create and save a destination, you can work with that data in [!DNL  Analytics]. However, it can take a few hours before data is available in your selected report suites. See [ Use the Audience Data in Analytics ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html). 
