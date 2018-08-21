---
description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configure a URL Destination
uuid: 90dcc92a-5656-454b-891c-8fa6861ec403
index: y
internal: n
snippet: y
translate: y
---

# Configure a URL Destination

To create a new URL destination, go to **[!UICONTROL  Audience Data > Destinations > Create New Destination]** and complete the sections as described below. 

## Basic Information {#section_7B13F3A2FD73432886D8FFCB377CBE8C}

This section contains fields and options that start the URL destination creation process. To complete this section: 

1. Click **[!UICONTROL  Basic Information]** to expose the controls.
1. Name the destination. Avoid abbreviations and special characters.
1. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
1. *(Optional)* In the **[!UICONTROL  Platform]** list, leave the default set to **[!UICONTROL  All]**. Currently, these options don't do anything. They're designed to support features that may be added at a later date.
1. In the **[!UICONTROL  Type]** list, click **[!UICONTROL  URL]**.
1. *(Optional)* Select an **[!UICONTROL  Auto-fill Destination Mapping]**. Options include: 


    * **[!UICONTROL  Segment ID]**: Automatically adds and sends the segment ID to the destination.
    * **[!UICONTROL  Integration Code Value]**: Automatically adds and sends the segment integration code to the destination mapping. The integration code is a unique identifier created and used by the customer. It is limited to 255 characters, maximum.


1. Click **[!UICONTROL  Next]** to go to the [!UICONTROL  Configuration] settings or click **[!UICONTROL  Data Export Labels]** to apply export controls to the destination.

## Data Export Labels {#section_24858C4E36234493ABF33DF39501C1E9}

This section contains options that apply [ data export controls ](../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C) to a URL destination. Skip this step if you do not use data export controls. To complete this section: 


1. Click **[!UICONTROL  Data Export Labels]** to expose the controls.
1. Select a label that corresponds to the data export control applied to the destination (see [ Add Export Labels to a Destination ](../../c_features/c_destinations/t_export_labels.md#task_A4BA30472E6F4687AC3F1B33F51909D9) for details).
1. Click **[!UICONTROL  Save]**.


## Configuration {#section_A8AB50168B674B46BE80771B9BAF37DD}

This section contains options that let you set a base URL and data delimiters passed in by the URL string. This section is optional. To complete this section: 


1. Click **[!UICONTROL  Configuration]** to expose the controls.
1. *(Optional)* Select the **[!UICONTROL  Serialize]** check box. This lets you send segments to a destination sequentially rather than making separate calls for each segment. Serialization helps make data transfers efficient. Selecting this check box exposes the URL and delimiter fields. For more information, see [ Standard and Serial Key-Value Pairs ](../../c_features/c_destinations/key-value-pairs.md#concept_4CAA6E54ECFE4291B8626BEBEE98088A). 

1. If you select **[!UICONTROL  Serialize]**, then you must also configure the URL and delimiter fields described below. 
<table id="table_6D14A180300B4EFA8324958CFE9854DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Base URL </span> </p> </td> 
   <td colname="col2"> <p>The base part of a standard HTTP URL that does not change. Also, you need to place the <span class="codeph"> %ALIAS% </span> <a href="../../c_features/c_destinations/destination-macros.md#reference_B2F4AE643702440D879EFFE4A3FAAEDB" format="dita" scope="local"> placeholder macro </a> in the base URL. </p> <p>Example: <span class="codeph"> http://www.myCompany.com/?%alias%... </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Secure URL </span> </p> </td> 
   <td colname="col2"> <p>The base part of a secure HTTPS URL that does not change. Also, you need to place the <span class="codeph"> %ALIAS% </span> <a href="../../c_features/c_destinations/destination-macros.md#reference_B2F4AE643702440D879EFFE4A3FAAEDB" format="dita" scope="local"> placeholder macro </a> in the base URL. </p> <p>Example: <span class="codeph"> https://www.myCompany.com/?%alias%... </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Delimiter </span> </p> </td> 
   <td colname="col2"> <p>The symbol that separates the segment variables in the URL string. This is usually a comma or semi-colon. Get this information from your destination partner. </p> </td> 
  </tr> 
 </tbody> 
</table>




## Segment Mappings {#section_45FF2A8E4EB648488578365DB5D15219}

This section lets you search for and add segments to your destination. To complete this section: 

1. Click **[!UICONTROL  Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL  Search and Add Segments]**box, start typing the name of a segment or click **[!UICONTROL  Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL  Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL  Edit Mapping] window.
1. In [!UICONTROL  Edit Mapping]: 


    * **[!UICONTROL  Mappings]**: Provide the key-value pairs used by the segment.
    * **[!UICONTROL  Start Date]** and **[!UICONTROL  End Date]**: Choose a start and end date for the destination. If the end date is blank, the destination never expires.


1. Click **[!UICONTROL  Done]**.
