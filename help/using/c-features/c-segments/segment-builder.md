---
description: Describes how to create segments with Segment Builder.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
index: y
internal: n
snippet: y
---

# Segment Builder {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## Create a Segment {#task_FC8DBBF9FA4447F9B60D5AFACA73332B}

### Segment Builder Section

<!-- 
t_create_segment.xml
-->

[!UICONTROL Segment Builder] consists of 3 separate sections: Basic Information, Traits, and Destinations Mapping. To create a segment, complete the required fields in the Basic Information and Traits sections. Destinations Mapping settings are optional. See the instructions below for additional help.

1. In the [Basic Information](../../c-features/c-segments/segment-builder.md#reference_9FC34B07E1944CE5A23974B8E58B2A18) section:
    * Name the segment. The maximum length of a segment name is 255 characters.
    * Set the segment status (active is default).
    * Choose a data source.
    * Select a profile merge rule to use for segment qualification.
    * Assign the segment to a storage folder.

2. In the [Traits](../../c-features/c-segments/segment-builder.md#reference_131791CC12A6431A8AD5F19F4FB48947) section:
    * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. Add another trait to create a trait group.
    * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. Search for traits by name, ID, description or data source. Click on a folder while searching to limit results to that folder and its subfolders. You can also filter traits by trait type.
    * Click and drag traits to create separate groups.
    * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
    * Hover over the clock icon to add [recency and frequency](../../c-features/c-segments/recency-and-frequency.md#concept_957D9E1977774D28A98ACEE6035E7B37) rules to the trait.
    * View segment population data as you add or remove traits. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../c-features/c-segments/segment-builder-data.md#section_ED9F6B29E9D541499E3FC7C0A1753FCE) in the Segment Builder.
    * Click **[!UICONTROL Save]** when done.

3. *(Optional)* Map a segment to a destination in the [Destination Mapping](../../c-features/c-segments/segment-builder.md#reference_D4D92F9F114449C9BC2A51A1C746D92F) section:

    * Search for the destination and click **[!UICONTROL Add Destination]**. Note, the destination must already exist before you can add it to a segment.
    * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#reference_9FC34B07E1944CE5A23974B8E58B2A18}

In [!UICONTROL Segment Builder], the Basic Information settings let you create new, or edit existing traits. To create a new segment, provide a name, a data source, and select a storage folder. All other fields are optional. Move on to the Traits section when done.

<!-- 
r_segment_basic_info_section.xml
-->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#reference_131791CC12A6431A8AD5F19F4FB48947}

In Segment Builder, the Traits section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click Add Trait. Save the trait (if finished) or move on to Destinations Mapping.

<!-- 
r_segment_traits_section.xml
-->

**Prerequisites:** Complete the required fields in the Basic Information section.

<table id="table_27644243716E4602B432E2C6C8AD9AA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Basic View</b> </td> 
   <td colname="col2"> <p>This section provides visual controls that let you: 
     <ul id="ul_27975947FADC4EAE86926CA02BB89BCC"> 
      <li id="li_91C49CB479F7468783111F30776977CE">Build new and manage existing segments. </li> 
      <li id="li_BAE3FE2305834A189508CB51F5AC5D06">Remove traits from a segment. </li> 
      <li id="li_E1AA7CA1A5C44C30A17023839552807D">Add up to 50 (maximum) traits to a segment. </li> 
      <li id="li_1DE7C4757DAB4FCDAF0628269B6DEFD4">Drag and drop traits to create new groups. </li> 
      <li id="li_E077F74E04ED448DAC0148A97B0EFD4F">View traits and trait groups in a segment. </li> 
      <li id="li_E1948B8951894F06965E620BCCDF582B">Set qualification criteria with Boolean expressions, comparison operators, and recency/frequency settings. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Code View</b> </td> 
   <td colname="col2"> <p>Opens a development environment that lets you create and manage traits, groups, and qualification requirements with code instead of the visual interface. The code view is useful if your segments: 
     <ul id="ul_C1CADB3BBDFF4F3484C36D737689B095"> 
      <li id="li_CE2BB4544993433F9AE2EC1F6A6BB09E">Contain more than 50 traits in an individual segment. <p>Note:  Segments are limited to 5000 traits (maximum). </p> </li> 
      <li id="li_EC7EE1F3681A40C89DD6128C4F90AF57">Contain many trait groups. </li> 
      <li id="li_EC072A80938F42598F11880C2C06C703">Have complex qualification requirements. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Search</b> </td> 
   <td colname="col2"> <p>Helps you find traits to add to a segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Real and Estimated Segment Size Data</b> </td> 
   <td colname="col2"> <p>See <a href="../../c-features/c-segments/segment-builder-data.md#concept_05EE3010E67F446E8818351292EF7372"> Trait and Segment Population Data in Segment Builder</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls Destinations Mappings Section {#reference_D4D92F9F114449C9BC2A51A1C746D92F}

In [!UICONTROL Segment Builder], the optional Destinations Mapping section lets you send segment data to a third-party cookie, URL, or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click Add Destination.

<!-- 
r_segment_destinations_map.xml
-->

**Prerequisites:** Complete the required fields in the Basic Information and Traits sections. Also, the destination must already exist.

### Destination Mappings Search Tools

The **[!UICONTROL Destination Mappings]** panel contains search tools as described in the table below.  

|  Search Type  | Description  |
|---|---|
| **Search by Destination Name** |Lets you search for a specific destination by name. To search, start typing. The field will auto-complete based on your search terms. Click **[!UICONTROL Add Destination]** when done.  |
| **Browse All Destinations** |Browse a list of *all* destinations available to you. Select and add destinations to your segment from the popup list.  |

## Fields in the Destination Mappings Pop-up Windows {#reference_D3871A197C21474091F940AB5498F98A}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] pop appears after you select a destination. This window displays static information about the destination and fields that vary depending on the destination type. Provide the required information in the empty fields to set up a destination mapping.

>[!NOTE]
>
>Publication dates are optional. When blank, the destination becomes active and never expires.

<!-- 
r_add_mappings_pop.xml
-->

### Cookie Destination Fields

In the Destination Mapping fields, specify the key-value pairs used to send data to the destination. Enter the key in the first field and the values in the second. Your cookie destination pop could look similar to this:

![](assets/cookie_modal.PNG)

### URL Destination Fields

In the URL and Secure URL fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### Server-to-Server Destination Fields

In the Destination Value field specify the value (part of a key-value pair) used to send data to the destination.

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_THIS]
>
>* [Create a Cookie Destination](../../c-features/destinations/manage-destinations.md#concept_2462AA1321984293A92CB174C41B3496)
>* [Create a URL Destination](../../c-features/destinations/manage-destinations.md#concept_51842672DFA943EA982B363E74D42DF8)
