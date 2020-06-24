---
description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
keywords: actionable logs, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actionable Log Files
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
---

# Actionable Log Files {#actionable-log-files}

[!UICONTROL Actionable Log Files] allow you to capture media data from ad server log files and use the data to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md). 

>[!NOTE]
>
>The text styles (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../reference/code-style-elements.md) for more information.

## Purpose {#purpose}

[!UICONTROL Actionable Log Files] streamline the way you capture impressions, clicks, and conversions from ad servers. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Getting Started {#getting-started}

To get started with [!UICONTROL Actionable Log Files], you need to import log data into [!DNL Audience Manager]. The following links will help you get started: 

* For [!UICONTROL Google DCM] logs, see [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.
* For [!UICONTROL Google Ad Manager] (formerly Google DFP) logs, see [Import DFP Data Files Into Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *and* contact your [!DNL Audience Manager] consultant.
* For other ad server logs, see [Data and Metadata Files](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you. 

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from ad server logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] connects to your ad server log storage, parses the information from the logs, and sends the log data as actionable signals to our [Data Collection Servers](../../reference/system-components/components-data-collection.md#dcs-pcs).

You still need to set up rule-based traits to capture the actionable signals. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

>[!IMPORTANT]
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). We discourage the use of both options, as this leads to an increase in frequency counts for traits.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] allow you to capture advertiser, business unit, creative, and campaign values in impression events, click events, and conversion events as signals from ad server logs.

Remember, in order to use this information for audience creation and segmentation, you need to set up the rule-based traits yourself.

### Actionable Signals from Google DCM logs {#dcm-logs-signals}

The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Header Name in Log File </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Example Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Available only for conversion events. </p> <p>Represents the numerical ID for the conversion activity in DCM. This field maps to the Activity ID from DCM. </p> <p> <p>Tip: You can capture multiple or specific conversion activities from DCM. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Available only for conversion events. </p> <p>This field maps to the Conversion ID in DCM. Indicates the activity preceding the user conversion from DCM. </p> <p>Accepted values are: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> for post-click conversions. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> for post-impression conversions. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> for un-matched conversions. The conversion cannot be matched to a previous activity. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">A UTC date and time for the impression, click, or conversion event. Represented in microseconds since 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>An integration code for your advertiser's data source. Note that this is not related to Audience Manager data sources.</p> <p>This field maps to the Advertiser Group ID from DCM. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Business Unit ID. This field maps to the Advertiser ID from DCM. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>The Campaign ID provided by DCM.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>The Creative ID provided by DCM. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> The sales amount in USD, to the power of -6. Multiply by 1.000.000 to see as a dollar amount.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indicates the event type. Audience Manager reads the event type from the DCM log file name and transforms it into an actionable signal. </p> <p>Accepted values are: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> for impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> for clicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> for conversions. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>The ID of the data source you use to capture DCM data. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!NOTE] {importance="high"}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn't available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.

<br>&nbsp;

### Actionable Signals from [!DNL Google Ad Manager] logs {#ad-manager-logs-signals}

The table lists the actionable signals from [!DNL Google Ad Manager] log files:


Header Name in Log File | Signal | Description
---------|----------|---------
`LineItemId` | `d_lineitem` | The numeric ID for the delivered Ad Manager line item
`OrderId` | `d_orderid` | The numeric ID for the Ad Manager order that contained the delivered line item and creative.
`CreativeId` | `d_creative` | The numeric ID for the delivered Ad Manager creative.
`-` | `d_event` | Indicates the event type. Audience Manager reads the event type from the DCM log file name and transforms it into an actionable signal. Accepted values are: <br> <ul><li>d_event = imp for impressions.</li><li>d_event = click for clicks.</li><li>d_event = conv for conversions.</li></ul>
`-` | `d_src` | The ID of the data source you use to capture DCM data. See [How to Create a Data Source](/help/using/features/manage-datasources.md).

The signals described in the table are captured in Audience Manager like a real-time HTTP call. The example call below contains information on a conversion event from Google Ad Manager. Calls do not necessarily have to include all the signals in the example call.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>The event timestamp provided in the [!DNL Google Ad Manager] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn't available for a data row in the [!DNL Google Ad Manager] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL Google Ad Manager] log file contains a malformed timestamp, we ignore the entire row.

<br>&nbsp;

### Actionable Signals from Generic Ad Server Logs {#generic-logs-signals}

First, you must deposit your ad server logs in our Amazon S3 buckets. To accomplish this, read [Data Files for Audience Optimization Reports and Actionable Log Files](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *and* contact your [!DNL Audience Manager] consultant. The table lists the actionable signals from generic log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Header Name in Log File </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Example Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Indicates whether a conversion is matched or not. Options include: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impression </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Click </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Unattributed or unknown </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> A UTC date and time for the impression, click, or conversion event. Use the <code>yyyy-MM-dd HH:mm:ss</code> format. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>An integration code for your advertiser's data source. Note that this field is not related to <a href="../../features/datasources-list-and-settings.md">Audience Manager data sources.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Business Unit ID.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>The Campaign ID from the log file.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>The Creative ID from the log file. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Purchase or other conversion amount. Data type: Float. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indicates the event type. Audience Manager reads the event type from the log file name and transforms it into an actionable signal. See <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">log files naming conventions</a>. </p> <p>Accepted values are: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> for impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> for clicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> for conversions. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>The ID of the data source you use to capture log data. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. Calls do not necessarily have to include *all* the signals in the example call. 

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Working with Actionable Signals in the Audience Manager UI {#actionable-signals-in-ui}

You can view your incoming actionable signals in the [Signals Search](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) interface. 

Go to **Audience Data** (1) > **Signals** (2) > **Search** (3) and select the **Actionable Log Files** (4) filter.

![Actionable Signals in UI](/help/using/integration/assets/alf-in-signals.png)

To create rule-based traits using your actionable signals, select **Actionable Log Files** (1), select the actionable signals that you want to use as trait rules (2), and press **Create Trait from Selected Signals** (3).

![Create traits from signals](/help/using/integration/assets/alf-create-trait.png) 


## Use Cases {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. This allows you, for example, to frequency cap the number of times a user is shown a particular creative, within a media campaign. Read [Instant Cross-Device Suppression](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) to learn how to do this. Other use cases include:

### Retarget Users

Retarget users who saw creative 123 but didn't click or convert and show them creative 456. Do this:

1. Create a trait to capture users who saw the creative. Let's say you name the trait [!DNL Creative Trait 123]. Use the trait rule:

   `d_creative == 123 AND d_event == imp`

2. Create a trait to capture users who click or convert. Let's say you name this one [!DNL Click and Converter]. Use the trait rule:

   `d_event == click OR d_event=conv`

3. Create a segment to populate with users who saw creative 123 but didn't click or convert. Name it [!DNL Retarget Users] and use the segment rule: 

   `Creative Trait 123 AND NOT Click and Converter`

4. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Use DCM Floodlight Activity in the Audience Optimization Reports or in Audience Lab

[Floodlight tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) enable advertisers to track user conversions. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Create a trait and use the following trait rule to capture a conversion from the ad server logs:

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab]. 

>[!MORELIKETHIS]
>
>* [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
