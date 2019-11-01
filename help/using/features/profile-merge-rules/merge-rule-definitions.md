---
description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph, the Adobe Experience Cloud Device Co-op, and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph, the Adobe Experience Cloud Device Co-op, and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Profile Merge Rule Options Defined
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
---

# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 [!UICONTROL Profile Merge Rules]. The fourth [!UICONTROL Profile Merge Rule] is available exclusively to customers who purchased the [!UICONTROL People-Based Destinations] add-on.

You build a [!UICONTROL Profile Merge Rule] by making a selection from the options described below, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

Profile Merge Rules allow for a number of rule combinations, each geared towards specific use cases. See the table below for details on when to use each rule combination.

| Cross-Device Option            | Device Option                                       | Availability                                                                                                                                                                                      | Evaluation Type     | Audience Lab Support | Use Cases                                                                               |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| No Cross-Device Profile        | Device Profile                                      | All customers                                                                                                                                                                                     | Real-time and batch | Yes                  | [Device Targeting](merge-rule-targeting-options.md#device-personalization)              |
| No Cross-Device Profile        | External Device Graph (includes Co-op Device Graph) | All customers                                                                                                                                                                                     | Real-time and batch | No                   | [Expanded Device Targeting](external-graph-use-cases.md#audience-expansion)             |
| Current Authenticated Profiles | No Device Profile                                   | All customers                                                                                                                                                                                     | Real-time only      | No                   | [Shared Device Targeting](merge-rule-targeting-options.md#target-shared-devices)        |
| Last Authenticated Profiles    | Device Profile                                      | All customers                                                                                                                                                                                     | Real-time and batch | Yes                   | [Online/Offline Targeting](merge-rule-targeting-options.md#device-household-targeting)  |
| Last Authenticated Profiles    | Profile Link Device Graph                           | All customers                                                                                                                                                                     | Real-time and batch | Yes                   | [Cross-device Targeting](profile-link-use-case.md#cross-device-personalization)         |
| Last Authenticated Profiles    | External Device Graph (includes Co-op Device Graph) | All customers                                                                                                                                                                                     | Real-time and batch | No                   | [Advanced Cross-Device Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| All Cross-Device Profiles      | N/A                                                 | Exclusive to [People-Based Destinations](../destinations/people-based-destinations-overview.md) customers | Batch only          | No                   | [Targeting for People-Based Destinations](merge-rule-targeting-options.md#all-cross-device)              |

## Profile Merge Rule Segment Evaluation {#segment-evaluation}

Depending on your [!UICONTROL Profile Merge Rules] configuration, Audience Manager can perform the segment evaluation in real-time, in batch, or both.

* Real-time segment evaluation requires the [!DNL DCS] to see visitors access your digital properties in real-time, to qualify for the segment.
* Batch segment evaluation is performed against previously qualified traits.
* [!UICONTROL Profile Merge Rules] that support both real-time and batch segment evaluation combine the real-time visitor activity with previously qualified traits.

## Profile Merge Rules Reporting Latency {#reporting-latency}

Real-time segment evaluation reflects immediately in the [!UICONTROL Profile Merge Rules] reports.

Batch segment evaluation can take up to 24 hours to reflect in the [Profile Merge Rules reports](profile-link-metrics.md).

## Cross-Device Options {#auth-options}

The [!UICONTROL Cross-Device Options] let you select authenticated and unauthenticated users and leverage their cross-device profile for segmentation. These options help you identify and reach specific users on a shared device. For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cross-Device Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> No Cross-Device Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use data collected from authenticated users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read data from the authenticated profile of the user who last logged in on the device. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. Upon authentication, new trait data gets written to the user's authenticated profile. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> All Cross-Device Profiles</span></b> </p> </td> 
   <td colname="col2"> <p>Tells Audience Manager to read data from all cross-device profiles, regardless of the authentication state. This option is only available for Audience Manager customers who have purchased the People-Based Destinations add-on.</p> </td>
  </tr>
 </tbody>
</table>

## Cross-Device Profile Options {#profile-options}

The [!UICONTROL Cross-Device Profile Options] lists your cross-device data sources. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](merge-rules-start.md#create-data-source)). You can select up to 3 cross-device data sources to use with each profile rule. The [!UICONTROL Authenticated Profile Options] are available when you choose **[!UICONTROL Current Authenticated Profiles]** or **[!UICONTROL Last Authenticated Profiles]**.

## Device Options {#device-options}

The [!UICONTROL Device Options] let you select the type of *`device profile`* used by a [!UICONTROL Profile Merge Rule]. A device profile is built from traits collected from anonymous browsing activity. At a minimum, a profile merge rule includes an authenticated option and a device option.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Device Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> No Device Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use the traits contained in the anonymous profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Device Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to use the anonymous device profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profile Link Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and up to 100 other devices that the user has authenticated from. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. It is ideal for customers who have a high level of authentication across their digital properties. The <span class="wintitle"> Profile Link</span> device graph is updated in real time. This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). See also, <a href="profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and up to 100 other devices using the links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>The <span class="keyword"> Device Co-op</span> is a digital cooperative where participating customers share device link information. The <span class="keyword"> Device Co-op</span> processes this data in a <span class="term"> device graph</span>. A device graph links devices together form device clusters. These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. The clusters represent a group of devices used by an unknown person. The <span class="keyword"> Device Co-op</span> shares these clusters among its members, which helps them deliver valuable and consistent cross-device experiences to their customers. </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Device Co-op Overview</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Membership Requirements</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Device Graph: Internal Processes and Output</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager and External Device Graphs</a> (PDF download). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Third-Party Device Graph Options</b> (Person and Household) </p> </td>
   <td colname="col2"> <p>These options let you build merge rules based on device graph technology provided by a third-party vendor. A third-party device graph provides: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistic and/or deterministic data. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Data at the person or household level. </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. Contact your account manager for more information or to get started. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Profile Merge Rules FAQ](../../faq/faq-profile-merge.md)
