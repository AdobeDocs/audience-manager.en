---
description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
---
# [!UICONTROL Audience Lab] {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.

## Overview {#audience-lab-overview}

[!UICONTROL Audience Lab] uses [Profile Link](../../features/profile-merge-rules/merge-rules-overview.md) to power cross-device testing. This helps ensure a user qualifies for the same test segment and receives the same treatment across devices. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

The [!UICONTROL Audience Lab] default view displays a card for each of the test groups. Click a card to access the **[!UICONTROL Test Group]** view. This view includes the following information:

* **[Test Group Information](../../features/audience-lab/audience-lab-information-view.md)**
* **[Test Group Reporting](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

Once you start creating multiple test groups with multiple test segments, it may be easier to use the search box to find a specific test group. You can search for a test group by:

* The name of the test group;
* The name of any of the test segments in your test group;
* The description of the test group.

![](assets/search_and_filter_audience_lab.png)

You can also filter your test groups by status. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## [!UICONTROL Status] {#status}

The status of a test group can be active, scheduled, paused, draft, or completed. More information on each of them in the table below:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Active </span></b> </p> </td> 
   <td colname="col2"> <p>An <i>active</i> test group means that data is currently being sent to destinations. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Scheduled </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>scheduled</i> test group is not yet active but cannot be edited anymore. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Paused </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>paused</i> test group does not currently send data to destinations. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Draft </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>draft</i> test group is not yet active and can still be edited. It does not yet send data to the mapped destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completed </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completed</i> test group has reached the end date you selected in the <b><span class="uicontrol"> Create Test Groups </span></b> wizard and has stopped sending reporting data. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Actions </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Edit </span></b> </p> </td>
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Available for active test groups. Allows you to pause sending the test segments to destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Make Active </span></b> </p> </td>
   <td colname="col2"> <p>Available for paused test groups. Allows you to resume sending the test segments to destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> View </span></b> </p> </td>
   <td colname="col2"> <p>Available for completed test groups. Allows you to view the reporting information the test has generated. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicate </span></b> </p> </td>
   <td colname="col2"> <p>Allows you to create a new test group with the same configuration as the one you are duplicating. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Delete </span></b> </p> </td>
   <td colname="col2"> <p>Allows you to delete a test group. The test segments will be unmapped from the destinations, the baseline segment and conversion traits associated to the test group are fully editable. An alert will prompt you to download the CSV file when you delete a test group to save the reporting if you wish. </p> </td>
  </tr>
 </tbody>
</table>
