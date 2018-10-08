---
description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Data Export Controls
uuid: fc3b63c9-54ec-4320-971f-69f8647d8acd
index: y
internal: n
snippet: y
translate: y
---

# Data Export Controls

Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.

## Overview {#section_496DA531EFED46E4BF7EEDE878746FB1}

[!UICONTROL Data Export Controls] let you classify [data sources](../c_features/datasources-list-and-settings.md#concept_DC7CC030739C436C947078C7877C15AD) and [destinations](../c_features/destinations/destinations.md#concept_5BDA346C376C4B719EA394108AB2735A). The classifications you apply determine when data can or cannot be exported to a destination. This feature consists of:

* ** [!UICONTROL Data Export Controls] **: When set on a data source, these controls restrict how that data source and its traits can be used. 
* ** [!UICONTROL Data Export Controls] **: When set on a destination, these labels identify how the destination uses data.

Based on the classifications applied to a data source and destination, the export controls stop you from:

* Adding traits to a segment when that segment is blocked by an export control/export label combination. 
* Sending any data to a destination if that destination is blocked by an export control/export label combination.

[!UICONTROL Data Export Controls] are available automatically. However, you need administrator permissions to add export controls to a data source. Adding export labels to a destination requires administrator permissions *or* sufficient privileges to create or edit a destination.

## Controls and labels defined {#section_8FCC7836D8F14C94A049FEF7754DE698}

[!UICONTROL Data Export Controls] provide the following controls to help you classify data sources and destinations.

To block data delivery, you must classify a data source with an export control and add an export label to a destination. If you apply export controls to a data source or destination only, this feature will not restrict data delivery. When set on both the data source *and* destination, the export controls will limit the traits you can add to a segment and prevent the segment from sending data to a destination.

Additionally, at least one export label must match an export control before data delivery restrictions take effect. For example, say you add the PII export control to a data source. Next, you add the on-site targeting label to a destination. In this case, export controls will not limit data delivery because the settings do not match. However, if you add the PII export label to the destination, the export controls will work.

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
   <td colname="col1"> <span class="uicontrol"> No restriction</span> </td> 
   <td colname="col2"> n/a </td> 
   <td colname="col3"> By default, export restrictions are not set on new data sources and destinations. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Cannot be tied to personally identifiable information</span> (PII) </td> 
   <td colname="col2"> <span class="uicontrol"> This destination may enable a combination with personally identifiable information (PII)</span> </td> 
   <td colname="col3">When selected, you cannot: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Add traits to segments mapped to destinations that use PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Map segments to destinations that use PII. </li> 
    </ul> <p>This is often required by third-party data providers and when using data sources that contain ad/media tracking information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Cannot be used for on-site ad targeting</span> </td> 
   <td colname="col2"> <span class="uicontrol"> This destination may be used for on-site ad targeting</span> </td> 
   <td colname="col3">When selected, you cannot: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Add traits to segments mapped to destinations that customize ad delivery based on a visitor's web-browsing history. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Map segments to destinations that customize ad delivery based on a visitor's web-browsing history. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Cannot be used for off-site ad targeting</span> </td> 
   <td colname="col2"> <span class="uicontrol"> This destination may be used for off-site ad targeting</span> </td> 
   <td colname="col3">These restrictions are used generally with When selected, you cannot: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Add traits to segments mapped to destinations that re-target users on other sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Map segments to destinations that re-target users on other sites. </li> 
    </ul> <p>Often required when working with data from social media platforms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Cannot be used for on-site personalization</span> </td> 
   <td colname="col2"> <span class="uicontrol"> This destination may be used for on-site ad personalization</span> </td> 
   <td colname="col3">When selected, you cannot: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Add traits to segments mapped to destinations that customize content based on user interests or web-browsing history. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Map segments to destinations that customize content based on user interests or web-browsing history. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#section_2D8964C80F304761A0A937CCAF9F987C}

To get started, review the data source and destination documentation. These articles provide instructions about how to add export controls and labels to your data sources and destinations.

* [Create a Data Source](../c_features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44) 
* [Add Data Export Labels to a Destination](../c_features/destinations/manage-destinations.md#task_A4BA30472E6F4687AC3F1B33F51909D9)

