---
description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Data Export Controls
uuid: de7f3608-c0cb-4049-973a-8be54525c600
---

# Data Export Controls {#data-export-controls}

[!UICONTROL Data Export Controls] prevent you from sending data to destinations when this action violates data privacy or data use agreements.

## Overview {#overview}

[!UICONTROL Data Export Controls] let you classify [data sources](../features/datasources-list-and-settings.md#data-sources-list-and-settings) and [destinations](../features/destinations/destinations.md). The classifications you apply determine when data can or cannot be exported to a destination. This feature consists of:

* **[!UICONTROL Data Export Controls]**: You can set Data Export Controls on *data sources*. When set on a data source, these controls restrict how that data source and its traits can be used.
* **[!UICONTROL Data Export Labels]**: You can set Data Export Labels on *destinations*. When set on a destination, these labels identify how the destination uses data. See [Add Data Export Labels to a Destination](/help/using/features/destinations/add-data-export-labels.md) to learn how to add export labels to a destination.

Based on the classifications applied to a data source and destination, the export controls stop you from:

* Adding a trait to a segment when the trait belongs to a data source that has a data export control that is incompatible with a data export label on one or more of the destinations that the segment is mapped to.
For example, say a segment is mapped to a destination with the export label **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Export controls stop you from adding a trait to that segment if the data source that the trait belongs to has a data export control that says **[!DNL Cannot be tied to personally identifiable information (PII)]**. 
* Sending any data to a destination destination has a data export label that is blocked by a data export control on any of:
  * The data source of an included trait;
  * The data source of a trait that is used in an included segment;
  * The profile merge rule leveraged by an included segment;
  * Any of the data sources that an included segment's profile merge rule uses.

[!UICONTROL Data Export Controls] are available automatically for all Audience Manager customers. However, you need administrator permissions to add export controls to a data source. Adding export labels to a destination requires administrator permissions *or* sufficient privileges to create or edit a destination.

## Controls and labels defined {#controls-labels}

[!UICONTROL Data Export Controls] provide the following controls to help you classify data sources and destinations.

To block data delivery, you must classify a data source with an export control and add an export label to a destination. If you apply export controls to a data source or destination only, this feature will not restrict data delivery. When set on both the data source *and* destination, the export controls will limit the traits you can add to a segment and prevent sending the segment members to a destination.

Additionally, at least one export label must match an export control before data delivery restrictions take effect. For example, say you add the [!UICONTROL PII] export control to a data source. Next, you add the on-site targeting label to a destination. In this case, export controls will not limit data delivery because the settings do not match. However, if you add the [!UICONTROL PII] export label to the destination, the export controls will block the export.

>[!IMPORTANT]
>
>You can not block the export of a segment by placing a data export control on the data source of the segment, you must set the control on either of:
> * The data sources of the traits used in the segment;
> * The profile merge rule leveraged by the segment;
> * Any of the data sources that the segment's profile merge rule uses.

<br>&nbsp;

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Export Controls for a Data Source </th> 
   <th colname="col2" class="entry"> Data Export Labels for a Destination </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No restriction</span></b> </td> 
   <td colname="col2"> n/a </td> 
   <td colname="col3"> By default, export restrictions are not set on new data sources and destinations. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be tied to personally identifiable information</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may enable a combination with personally identifiable information (PII)</span></b> </td> 
   <td colname="col3">When selected, you cannot: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Add traits to segments mapped to destinations that use PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Map segments built with a trait from the data source to destinations that use PII. </li> 
    </ul> <p>This is often required by third-party data providers and when using data sources that contain ad/media tracking information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be used for on-site ad targeting</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may be used for on-site ad targeting</span></b> </td> 
   <td colname="col3">When selected, you cannot: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Add traits to segments mapped to destinations that customize ad delivery based on a visitor's web-browsing history. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Map segments built with a trait from the data source to destinations that customize ad delivery based on a visitor's web-browsing history. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be used for off-site ad targeting</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may be used for off-site ad targeting</span></b> </td> 
   <td colname="col3">These restrictions are used generally with When selected, you cannot: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Add traits to segments mapped to destinations that re-target users on other sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Map segments built with a trait from the data source to destinations that re-target users on other sites. </li> 
    </ul> <p>Often required when working with data from social media platforms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be used for on-site personalization</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may be used for on-site ad personalization</span></b> </td> 
   <td colname="col3">When selected, you cannot: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Add traits to segments mapped to destinations that customize content based on user interests or web-browsing history. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Map segments built with a trait from the data source to destinations that customize content based on user interests or web-browsing history. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#workflow}

To get started, review the data source and destination documentation. These articles provide instructions about how to add export controls and labels to your data sources and destinations.

* [Create a Data Source](../features/manage-datasources.md#create-data-source) 
* [Add Data Export Labels to a Destination](../features/destinations/add-data-export-labels.md)