---
description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: Overview and Mappings for Metadata Files
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
index: y
internal: n
snippet: y
---

# Overview and Mappings for Metadata Files{#overview-and-mappings-for-metadata-files}

A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.

## Overview {#section_BDE34D99F18643F1A57D454DE4A7CECC}

A review of metadata and how it's used. A metadata file must be accompanied by a data file. The metadata file contents match data file information to related, human-readable labels in the report menus. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#concept_76D2C04AA9904203BDC74E4D38D86C89).

### Metadata Files Contain Data About Other Data

A metadata file contains information about other types of data. To help you understand how this works, let’s review how [!DNL Audience Manager] receives data. During an impression or click event, [!DNL Audience Manager] receives data in an URL string known as an event call. The event call organizes information into sets of defined key-value pairs. The values in a key-value pair contain of numeric data. The metadata file contains names and other readable information corresponding to the ID in each key-value pair.

### Metadata Links IDs to Readable Names

The metadata file is required to tie a numeric ID to a readable name. As an example, say an event call contains a creative ID in a key-value pair like this: `d_creative:1234`. Without a metadata file, this creative would show up as 1234 in an options menu. However, a properly formatted metadata file can tie this creative to back to a real name like “Advertiser Creative A,” which is a name you can read and recognize in a report.

### When Do You Need a Metadata File

First, a metadata file, and all of the parameters listed below, are required in an event call when you want to use the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md#concept_D66D2C58493E48BDAFF2F95BBB508946).

Second, you need a metadata file if you’re sending your own data to [!DNL Audience Manager] or if you want to see data in the reports from other providers we’re not integrated with. For example, [!DNL Audience Manager] has an integration with Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md#task_5BBF62BBAA7D43AFA6DCCF53C6DBEF00) (DCM). Because of this relationship, [!DNL Audience Manager] can associate IDs with names and descriptions used by the report options. Without an integration, we can still ingest data, but the report options will show numeric IDs instead of descriptive name.

![](assets/metadata_menu.png)

## File Mappings {#section_92AD346141F3414BA9FEDFE1E9306CFF}

The following table lists the key-value pairs that hold data used by the [!UICONTROL Audience Optimization] reports. If you need to use a metadata file, it would contain human-readable information that corresponds to the values in these key-value pairs. The values for these keys accept integers only (data type INT). Note, *italics* indicates a variable placeholder. Other elements are constants or keys and do not change.

>[!IMPORTANT]
>
>If you're using the [!UICONTROL Audience Optimization] reports, *all* of these values are required in the event call.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report Option </th> 
   <th colname="col2" class="entry"> Metadata Key-Value Pairs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_adsrc = <span class="varname"> data source ID or integration code</span></span> </p> <p>This is the advertiser's data source ID or integration code provided when creating a data source. See <a href="../../../c-features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business Unit (BU) </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_bu = <span class="varname"> business unit ID</span></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_campaign = <span class="varname"> campaign ID</span></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_creative = <span class="varname"> creative ID</span></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Accepts 2 different key-value pairs: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <span class="codeph">d_exchange = <span class="varname"> ID for the exchange that served the ad</span></span> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <span class="codeph">d_site = <span class="varname"> ID for the site an ad served on</span></span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion Order (IO) </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_io = <span class="varname"> insertion order ID</span></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Platform </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_src = <span class="varname"> data source ID</span></span> </p> <p>This is the <a href="../../../c-features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> ID for the platform providing metadata information (e.g., DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_tactic = <span class="varname"> tactic ID</span></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_vert = <span class="varname"> vertical ID</span></span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDs Shape File Names, Contents, and Delivery Paths {#section_3FB8AE59CE0149DFAC076D32D792EE0B}

The IDs passed in by these key-value pairs help create the metadata file name and its contents. The following sections and illustrations demonstrate how this works. These examples build a file that contains the name of a creative in a campaign, but other combinations are possible.

### Event Call

In this example we'll create a metadata file that brings creative names in to an [!UICONTROL Audience Optimization] report. To do this, we need to extract creative, campaign, and data source IDs from an event call.

![](assets/metadata_file_event.png)

### File Name

The file name is based on the creative, campaign, and data source IDs. In this case, compare the differences here between the key-value data in an event call and how it's used in a file name.

In a file name:

* The data source key changes to `dpid` from `d_src`. 

* The creative and campaign IDs represent a category rather than an actual identifier.

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#concept_729806531D4547A6B5870BEA199FB4A9).

### File Contents

In this example, the file contents reflect the creative and campaign IDs passed in on the event call. The new element here is a readable name. Once processed, the name in this file will appear as an option in the Creative menu of an [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md#concept_5E422498650E40FD9744ABF290750107).

### File Delivery

After you name and add data to a file, you send it to an Amazon S3 storage directory provided by [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md#concept_679079B06314446BA34B9F2BE8050D03) and [Status Updates for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md#concept_B42172A8E6394E889DCF367AA01B4583). 

>[!MORE_LIKE_THIS]
>
>* [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#concept_76D2C04AA9904203BDC74E4D38D86C89)
>* [Capturing Campaign Click Data via Pixel Calls](../../../c-integration/media-data-integration/click-data-pixels.md#concept_E487584D9DBF4D7A8A16B745DAD818CD)
>* [Capturing Campaign Impression Data via Pixel Calls](../../../c-integration/media-data-integration/impression-data-pixels.md#concept_83852AB68E344D4F8933665C895322C2)
