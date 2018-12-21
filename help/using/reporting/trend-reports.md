---
description: A Trend report returns trend data on traits and segments.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Trend Reports
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
---

# Trend Reports{#trend-reports}

A Trend report returns trend data on traits and segments.

## Trend Reports {#concept_BE18204086E04825925E99B7DB6ED717}

A [!UICONTROL Trend] report returns trend data on traits and segments.

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ( [!UICONTROL RBAC]) to extend user-group permissions to the [!UICONTROL Trend] reports. Users can see only those traits and segments in reporting that they have permissions to view. [!UICONTROL RBAC] functionality lets you control what reporting data internal teams are able to view. For example, an agency that manages different advertiser accounts can configure user-group permissions so that a team that manages Advertiser A's account cannot see Advertiser B's reporting data.

Run a [!UICONTROL Trend] report when you need to:

* Review trend data by traits and segments. 
* Track trends by 1, 7, 14, 30, 60, and 90-day intervals. 
* Compare trait and segment trends over time. 
* Identify strong or poor performance traits and segments. 
* Export data (.csv format) for further analysis and sharing.

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports_border.jpg)

1. Configure the following options:

   **Report Type:** Select the desired report type (Trait or Segment).

   **Date Range:** Specify the date range for the report (start date and end date).

   **Display Interval:** Specify the display interval (1, 7, 14, 30, 60, and 90-day intervals). 

1. Search for a trait or segment by name or ID. 
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side. 
1. Generate the report to display in data in graphical format or export the report to CSV format.

## Run a Trend Report {#task_1FDC709F23E34B9FB5B6752BB6C7E886}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. Click the date boxes to display a calendar, then select the starting and ending dates for your report.
1. Specify the display interval: by 1, 7, 14, 30, 60, or 90-day.
1. Search for a trait or segment by name or ID.
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time. 
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   These options ignore all folders and graphs only individually selected traits or segments.

   Or

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] are calculated for [!UICONTROL Rule-based Traits] only.

1. (Optional) Mouse over individual traits or segments to display the number of visits and the date for each data point.

   You can click the column headers in the table to sort the results in ascending or descending order. 

For [!UICONTROL Trended Trait] reports, zeroes indicate that [!DNL Audience Manager] did not collect data for that day. Blank entries indicate that the trait didn't exist. The following example shows examples of both types of entries:

![](assets/trended_data.png)

