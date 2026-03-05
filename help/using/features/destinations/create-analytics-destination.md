---
description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configure an Analytics Destination
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
TQID: https://experienceleague.adobe.com/Fm25UT69AXSh-cXo6MXGQwW-17LFy8dqs3-STiWKDeA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Configure an Analytics Destination

## Requirements {#requirements}

To configure an Analytics destination, your Audience Manager user must have Admin permissions. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) in the Administration Guide. Note that having the `CREATE_DESTINATIONS` [wildcard permission](/help/using/features/administration/administration-overview.md#wild-card-permissions) is not sufficient to create Analytics destinations.
For further requirements, see Prerequisites in [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Your Default Analytics Destination and New Analytics Destinations

|  Analytics Destination Type |  Description |
|---|---|
|  Default |  The name of this default destination is "Adobe Analytics," which you can edit. Mapped report suite IDs appear in folder storage for your Audience Manager traits and segments. <br>&nbsp; Audience Manager creates one destination automatically if your account has: <br>&nbsp; <ul><li>Met the requirements described in the [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) documentation.</li><li>A [report suite](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li></ul>|
|  New | To create new Analytics destinations, go to Audience Data > Destinations > Create New Destination and follow the steps for each section described below. |

## Audience Manager segment qualifications in Adobe Analytics {#segment-qualifications}

When sending segment information to an Analytics destination, Audience Manager only sends the segments that the visitor qualified for. If a visitor stops qualifying for a segment, this information is _not_ forwarded to Adobe Analytics.

For example, consider the segment rules below:

* Segment A: Trait 1 AND Trait 2
* Segment B: Trait 1 AND NOT Trait 2

In Analytics reports, a profile may be shown as qualified for both segments, even though it stopped qualifying for Segment B.

## Step 1: Provide Basic Information

This section contains fields and options that start the Analytics destination creation process. To complete this section:

1. Click **Basic Information** to expose the controls.
2. Name the destination. Avoid abbreviations and special characters.
3. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
4. *(Optional)* In the **Platform** list, leave the default set to **All**. Currently, these options don't do anything. They're designed to support features that may be added at a later date.
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. You cannot change these settings.

![basicinformation](assets/basicinformation.png)

## Step 2: Configure Data Export Controls

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **Data Export Controls** to expose the controls.
1. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/add-data-export-labels.md) ). For Analytics destinations, the PII check box is selected by default.
1. Click **Save**.

![exportcontrols](assets/exportControls.png)

## Step 3: Map Report Suites

The Configuration section lists your Analytics Report Suites that have been enabled for server-side forwarding. If you have multiple Analytics destinations, the report suites assigned to these destinations will be mutually exclusive and enforced by Audience Manager. To complete this section:

1. Click **Configuration** to expose the controls.
1. Select one (or more) report suites that you want to send segments to.
1. Click **Save**.

![reportsuites](assets/reportSuites.png)

## Step 4: Segment Mappings

This section provides options that let you map segments automatically or manually.

|  Mapping Option |  Description |
|---|---|
|  Automatically map all current and future segments |  Selected by default, this feature sends all segments that a visitor qualifies for, on a per-hit basis, to Analytics. <br>&nbsp; If a visitor belongs to more than 150 Audience Manager segments on a single hit, only the 150-most recently qualified segments are sent to Analytics, while the remaining list is truncated. An additional flag is sent to Analytics signifying that the segment list was truncated. This action displays as "Audience limit reached" in the Audiences Name dimension and "1" in the Audiences ID dimension. See the [FAQ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) for details. <br>&nbsp; Also, this option affects destination availability in [Segment Builder](/help/using/features/segments/segment-builder.md). For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. The Analytics destination appears grayed-out and shows "Analytics" in the Type column of the Destination browser. |
|  Manually map segments | This option exposes search and browse controls that let you choose which segments you want to send to Analytics. <br>&nbsp; To search for a segment: <br>&nbsp; <ol><li>Type the segment name or ID in the search field.</li><li>Click <b>Add.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>&nbsp; To browse for a segment: <ol><li>Click <b>Browse all segments</b>. This exposes a list of available segments.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. You can't change the mappings, start, or end dates during the beta release.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Next Steps

After you create and save a destination, you can work with that data in Analytics. However, it can take a few hours before data is available in your selected report suites. See [Use the Audience Data in Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
