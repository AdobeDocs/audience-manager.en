---
description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Overlap Reports  Update Schedule and Minimum Segment Size
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
---
# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

Describes the trait and segment size and creation time requirements required by the Overlap report update process.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] reports update weekly on Sunday. Report pre-processing begins on Saturday. This affects how new or existing segments appear in an overlap report on Monday. To be included in an overlap report:

* A segment must contain a minimum of 70,000 total real-time users during the last 14 days.
* A trait must contain 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference.md) during the last 14 days.
* A segment must have been created prior to 12 AM Thursday UTC (2 full days before the weekly overlap report update process begins). 
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Size Too Small</b> </p> </td> 
   <td colname="col2"> <p>Let's say you create a segment before 12 AM Thursday UTC, but it contains less than 70,000 total real-time users. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. Note, also, the segment must meet the required user count on, or prior to, the Thursday cutoff period. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Created Too Late</b> </p> </td> 
   <td colname="col2"> <p>Let's say you create a segment on Friday and it contains more than 70,000 total real-time users. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Trait-to-Trait Overlap Report](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Segment-to-Trait Overlap Report](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Segment-to-Segment Overlap Report](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
