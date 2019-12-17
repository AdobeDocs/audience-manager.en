---
description: 
keywords: 
seo-description: 
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Activity Usage Reporting
topic: Activity Usage Reporting
---

# Activity Usage Reporting

## Overview {#overview}

The [!UICONTROL Activity Usage Report] helps you view and track your Audience Manager usage, giving you a clear idea of how your usage is comparing to your commitment.

Additionally, you can download the usage report whenever you need, for record keeping and custom analysis.

## Considerations {#considerations}

## Use Cases {#use-cases}

There are two main use cases of the [!UICONTROL Activity Usage Report]:

* **Tracking actual usage against your usage commitment**: Most customers have a monthly activity commitment that gets annualized. While this report is not a billing report, it can provide helpful guidance as to whether you are exceeding the committed usage.
* **Validation for implementation changes**: If you recently updated your implementation, such as setting up Analytics server-side forwarding, or changing your Target server call settings, this report can help you check whether the new activity volume is in line with your expected volume.  

## Using the Activity Usage Report {#using}

To see the [!UICONTROL Activity Usage Report], log in to your Audience Manager account, and go to **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

Next, use the **[!UICONTROL Date Filter]** to select the time interval to generate the report for. You can choose between 30, 60, 90 days, or a custome date range.

Once your report loads, you can see a breakdown of your activity for the selected period, for the following activity types:

* **[!UICONTROL Server Calls]**:  Data collection and data retrieval calls to Audience Manager conducted in an onsite, mobile, e-mail, or other tagged environment;
* **[!UICONTROL Pixel Calls]**: Data collected from ad or email impression calls made to Audience Manager. These require the presence of the `d_event` parameter in the query string.
* **[!UICONTROL Onboarded Records]**: Records ingested from your own CRM or other offline data files, such as call center records, mobile IDs, etc.
* **[!UICONTROL Log File Records]**: Ad engagement data ingested into Audience Manager from an ad server log file.


## Exporting Activity Usage Reports {#export}

The **[!UICONTROL Onsite Server Calls Breakdown]** and **[!UICONTROL Onboarded Records Breakdown]** reports provide the most granular insight of source data available for these activities. The volume attributed to these breakdowns is based on your implementation.

### Onboarded Records Breakdown {#onboarded-breakdown}

This report contains onboarded records broken down by data source.

### Onsite Server Calls Breakdown {#onsite-breakdown}

This report contains a breakdown of server calls from three sources: Analytics, Target, and [!UICONTROL Other].

* **[!UICONTROL Analytics]**: These are billable server calls passed from all Adobe Analytics instances to Audience Manager, including server-side forwarding. Secondary server calls or duplicate server calls (as in the case of server side forwarding from multiple report suites) are not billable activities, so they are not included in this breakdown.
* **[!UICONTROL Target]**: These are server-side calls from Adobe Target to Audience Manager, to retrieve Audience Manager segment data as part of a server-to-server integration.
* **[!UICONTROL Other]**: Includes calls from any other website or system (partner sites, direct server calls, etc.), mobile browser/app calls via the SDK, DIL, event calls, and DCS calls. Also includes calls from Target if set up as a cookie integration (rather than server-to-server).  


Reach out to your Adobe consultant or Customer Care for further questions.
