---
description: Answers to common Profile Merge Rule and device graph questions.
keywords: Organization ID
seo-description: Answers to common Profile Merge Rule and device graph questions.
seo-title: Profile Merge Rules and Device Graph FAQ
solution: Audience Manager
title: Profile Merge Rules and Device Graph FAQ
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
---

# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

Answers to common Profile Merge Rule and device graph questions.

<!-- profile-merge-faq.xml -->

## Device Graph Basics {#device-graph-basics}

**What is a device graph?**

A device graph is a set of ID mappings that defines groups of anonymous devices. It associates these devices to a person or household based on common elements in the signals collected from each device. These signals help identify devices at the individual or household level.

&nbsp;

**What is an external device graph?**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

&nbsp;

**What are some common use cases for using an external device graph in a [!UICONTROL Profile Merge Rule]?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. The segment itself may have multiple uses for example, targeting an audience of prospects with an ad served by a DSP or personalizing a customer’s on-site experience via an on-site personalization platform. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

&nbsp;

**Does Audience Manager provide global support for external device graphs?**

No. External device graphs are available in the United States and Canada only.

&nbsp;

**How often does [!DNL Audience Manager] update external device graph data?**

Once a week.

&nbsp;

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**How does [!DNL Audience Manager] use a device graph?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* Merge multiple device profiles together. This creates a single superset of traits.
* Evaluate the trait superset for segment qualification (rather than evaluating each device profile individually).
* Add qualified devices to available segments.

&nbsp;

**How many [!UICONTROL Profile Merge Rules] can I create?**

Currently, you can create a maximum of 4 [!UICONTROL Profile Merge Rules]. The fourth Profile Merge Rule ([!UICONTROL All Cross-Device Profiles]) is only available to customers who purchase the [!UICONTROL People-Based Destinations] add-on.

&nbsp;

**How many device profiles does [!DNL Audience Manager] merge and read when using a device graph in a [!UICONTROL Profile Merge Rule]?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 99 other additional device profiles linked by your selected device graph option.

&nbsp;

**Which devices qualify for a segment when using a device graph in a [!UICONTROL Profile Merge Rule]?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

&nbsp;

**Where can [!DNL Audience Manager] send segments that have been qualified by a [!UICONTROL Profile Merge Rule] that uses a device graph?**

[!DNL Audience Manager] can send segments to a destination in batch files or in real-time.

&nbsp;

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**How does [!DNL Audience Manager] un-segment a device when it is no longer qualified for a segment with a [!UICONTROL Profile Merge Rule] that uses a device graph?**

Audience Manager merges up to 100 devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. If the unsegment signal is issued, the current device and up to 99 additional devices will be removed from the segment in the destination. For more information about un-segmentation, see [Profile Merge Rules and Device Un-Segmentation Processes](../features/profile-merge-rules/merge-rule-unsegment.md).

&nbsp;

**If a destination can un-segment devices, will devices be removed from segments by [!UICONTROL Profile Merge Rules] that use a device graph?**

Yes. See the explanation above.

&nbsp;

**If I build a segment with a [!UICONTROL Profile Merge Rule] that uses a device graph and the segment is using both real-time and on-boarded data, will my segment be updated as the on-boarded data changes?**

Yes.

&nbsp;

**Do segment size estimates include devices that qualify for a segment based on connections provided by a [!UICONTROL Profile Merge Rule] that uses a device graph option?**

No. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html).

&nbsp;

**Does [!UICONTROL Addressable Audiences] include devices that qualify for a segment based on connections provided by a [!UICONTROL Profile Merge Rule] that uses a device graph option?**

Yes.

&nbsp;

**If a segment uses a [!UICONTROL Profile Merge Rule] with [!UICONTROL No Cross-Device Profile] and the traits which qualify devices for the segment are only stored on the cross-device profile, will the total population of the segment be 0?**

Yes. Audience Manager will not count the traits stored on the cross-device profile in the segment evaluation when the Profile Merge Rule is set to [!UICONTROL No Cross-Device Profile].

&nbsp;

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**How does [!DNL Audience Manager] calculate trait frequency with a [!UICONTROL Profile Merge Rule] that uses a device graph?**

The trait frequency is defined by the sum of the number of qualifications for a specific trait across multiple devices. To help you understand this, take a look at the following use case.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Device A and Device B are linked by a device graph. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">A single segment (Segment 1) composed of a single trait (Trait 1), where Trait 1 has a frequency of 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> reads and merges the device profiles for Device A and Device B. From this, we see the following: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Device A has qualified for Trait 1 three times. It has a frequency of 3 for Trait 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Device B has qualified for Trait 1 five times. It has a frequence of 5 for Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> sums the frequency for Trait 1 and uses 8 (3 + 5 = 8) to decide segment qualification. Device A and Device B qualify for Segment 1 because it has a frequency of 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

&nbsp;

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**Can I see the number of devices that can be reached by a [!UICONTROL Profile Merge Rule] that uses a device graph?**

Yes. Reports return data at the [!UICONTROL Profile Merge Rule] level. Report data is updated daily. Data is based on the devices seen in your account, not those linked by a device graph. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

&nbsp;

**Can I see the number of devices qualified for a specific segment in *real-time* with [!UICONTROL Profile Merge Rules] that use a device graph?**

Yes. The real-time population metric captures segment qualifications for the current device (the device seen in real-time) using the profiles from all of the devices linked by a device graph.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Suppose we have: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 built on these traits and qualification logic: Segment 1 = Trait A and Trait B and Trait C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 device profiles: Device 1 (current device), Device 2 (device graph), Device 3 (device graph). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p>Each available trait is associated with a device: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Device 1 : Trait A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Device 2 : Trait B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Device 3 : Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given the previous elements, the total population for Segment 1 is one. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. This means Devices 1, 2, and 3 qualify for Segment 1, but, as noted above, only Device 1 is included in the real-time segment population. This is because: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Devices 2 and 3 are associated to Device 1 by a device graph but they are not interacting with the DCS at the same time as Device 1. </li> 
     </ul> </p> <p>As a result, Devices 2 and 3 are not included in the real-time segment population metric. </p> </td> 
  </tr> 
 </tbody> 
</table>

&nbsp;

**Can I see the total number of devices qualified for a specific segment with a [!UICONTROL Profile Merge Rule] that uses a device graph?**

Yes. The total segment population metric includes the additional devices that have qualified for a segment based on the connections from a device graph.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Suppose we have: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 built on these traits and qualification logic: Segment 1 = Trait A and Trait B and Trait C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 device profiles: Device 1 (current device), Device 2 (device graph), Device 3 (device graph). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associations</b> </p> </td> 
   <td colname="col2"> <p>Each available trait is associated with a device: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Device 1 : Trait A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Device 2 : Trait B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Device 3 : Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given the previous elements, the total population for Segment 1 is three (3). </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. This means Devices 1, 2, and 3 qualify for Segment 1 and all three are included in the total population. </p> </td> 
  </tr> 
 </tbody> 
</table>

&nbsp;

**Are devices that qualify for a segment with a [!UICONTROL Profile Merge Rule] that uses a device graph included in the [!UICONTROL Interactive] reports, [!UICONTROL Overlap] reports and [!UICONTROL Audience Optimization] reports?**

No.

**Why do I see zero segment population for segment exports to Adobe Campaign after March 16, 2020?**

In late 2019, we have release a series of Profile Merge Rules enhancements to improve the accuracy of batch files generated using cross-device IDs. These enhancements will be strictly honored in your Audience Manager instance starting from Monday, March 16, 2020. Consquently, segments mapped to a destination using a cross-device IDs will stop producing exports in some Profile Merge Rules configurations.

To ensure the correct integration between your Audience Manager instance and destinations using cross-device IDs, such as Adobe Campaign, make sure you meet the following requirements:

1. Review the Profile Merge Rule used by the segments mapped to your Adobe Campaign Declared ID destination. The Profile Merge Rule must use the [!UICONTROL Last Authenticated Profile] option, so all authenticated profiles could be included in the exports. If your Profile Merge Rule is using a different option, switch it to [!UICONTROL Last Authenticated Profile].
2. Select the Adobe Campaign Declared ID data source in the Profile Merge Rule settings.

>[!NOTE]
>
> We have increased the Profile Merge Rule limit by 1 for customers facing this situation, so that you can create a dedicated Profile Merge Rule for the segments mapped to the Adobe Campaign Declared ID destination, without changing the Profile Merge Rules for other use cases.

>[!MORELIKETHIS]
>
>* [Profile Link](../features/profile-merge-rules/profile-link-use-case.md)
