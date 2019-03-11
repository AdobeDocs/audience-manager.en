---
description: Actionable Log Files allow you to capture media data from Google DCM log files and use the data to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to use pixel calls.
keywords: actionable logs
seo-description: Actionable Log Files allow you to capture media data from Google DCM log files and use the data to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to use pixel calls.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actionable Log Files
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
---

# [!UICONTROL Actionable Log Files] {#actionable-log-files}

[!UICONTROL Actionable Log Files] allow you to capture media data from [!DNL Google DCM] log files and use the data to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to use pixel calls.

<ul class="simplelist"> 
 <li> <a href="../../integration/media-data-integration/actionable-log-files.md#section_42B595E75E7A42E589F5E166968A1311"> Purpose </a> </li> 
 <li> <a href="../../integration/media-data-integration/actionable-log-files.md#section_DD0AAAB29999453889CB3C86D2F4EFF5"> Getting Started </a> </li> 
 <li> <a href="../../integration/media-data-integration/actionable-log-files.md#section_4608990C8D0D43AE8FDC33081543E5E2"> Working with Actionable Log Files </a> </li> 
 <li> <a href="../../integration/media-data-integration/actionable-log-files.md#section_F23E910753EB4241BFD8B76262526F18"> Actionable Signals </a> </li> 
 <li> <a href="../../integration/media-data-integration/actionable-log-files.md#section_09EB4686F5204452A39A7C2700D44E49"> Use Cases </a> </li> 
</ul>

>[!NOTE]
>
>The text styles ( `monospaced text`, *italics*, brackets [ ] ( ), etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../reference/code-style-elements.md#reference_59D0BD0EDB424A65853460D91CCA35D9) for more information.

## Purpose {#section_42B595E75E7A42E589F5E166968A1311}

[!UICONTROL Actionable Log Files] streamline the way you capture impressions, clicks, and conversions from ad servers. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Getting Started {#section_DD0AAAB29999453889CB3C86D2F4EFF5}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md#concept_D66D2C58493E48BDAFF2F95BBB508946), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md#task_5BBF62BBAA7D43AFA6DCCF53C6DBEF00) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance="high"}
>
>[!UICONTROL Actionable Log Files] work only with [!DNL Google DCM] log files.

## Working with Actionable Log Files {#section_4608990C8D0D43AE8FDC33081543E5E2}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] connects to your [!DNL Google Cloud] storage, parses the information from [!DNL DCM] logs, and sends the log data as actionable signals to our [Data Collection Servers](../../reference/system-components/components-data-collection.md#section_DEB68BEDDB4D4BCDAF50653D3F4568E2).

You still need to set up rule-based traits to capture the actionable signals. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md#task_E42901E227CE4123B3EE92074B16ACA2). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#section_F23E910753EB4241BFD8B76262526F18) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {importance="high"}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of* [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md#concept_83852AB68E344D4F8933665C895322C2). We discourage the use of both options, as this leads to an increase in frequency counts for traits.

## Actionable Signals {#section_F23E910753EB4241BFD8B76262526F18}

Signals are the [smallest data units](../../reference/signal-trait-segment.md#concept_7550A48FE3F1415FACF0E077CFAB155F) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] allow you to capture advertiser, business unit, creative, and campaign values in impression events, click events, and conversion events as signals from [!DNL DCM] logs.

Remember, in order to use this information for audience creation and segmentation, you need to set up the rule-based traits yourself. The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Signal </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Example Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_event</span> </p> </td> 
   <td colname="col2"> <p>Indicates the event type from DCM. </p> <p>Accepted values are: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <span class="codeph"> d_event = imp</span> for impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <span class="codeph"> d_event = click</span> for clicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <span class="codeph"> d_event = conv</span> for conversions. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> imp, click, conv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_conversion</span> </p> </td> 
   <td colname="col2"> <p>Available only for conversion events. </p> <p>Represents the numerical ID for the conversion activity in [!DNL DCM]. This field maps to the Activity ID from [!DNL DCM]. </p> <p> <p>Tip: You can capture multiple or specific conversion activities from [!DNL DCM]. Create traits using <span class="codeph"> d_conversion = activity ID</span> for each conversion activity from [!DNL DCM]. </p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 24122</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_conversionType</span> </p> </td> 
   <td colname="col2"> <p>Available only for conversion events. </p> <p>This field maps to the Conversion ID in [!DNL DCM]. Indicates the activity preceding the user conversion from [!DNL DCM]. </p> <p>Accepted values are: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <span class="codeph"> 1</span> for post-click conversions. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <span class="codeph"> 2</span> for post-impression conversions. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <span class="codeph"> 0</span> for un-matched conversions. The conversion cannot be matched to a previous activity. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 0,1,2</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_adsrc</span> </p> </td> 
   <td colname="col2"> <p>Advertiser ID. This field maps to the Advertiser Group ID from [!DNL DCM]. </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 134243</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_bu</span> </p> </td> 
   <td colname="col2"> <p>Business Unit ID. This field maps to the Advertiser ID from [!DNL DCM]. </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 563332</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_campaign</span> </p> </td> 
   <td colname="col2"> <p>The Campaign ID provided by [!DNL DCM]. </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 7892520</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_creative</span> </p> </td> 
   <td colname="col2"> <p>The Creative ID provided by [!DNL DCM]. </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 224221</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_src</span> </p> </td> 
   <td colname="col2"> <p>The ID of the data source you use to capture [!DNL DCM] data. See <a href="../../features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> 743</span> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance="high"}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn't available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.

## Use Cases {#section_09EB4686F5204452A39A7C2700D44E49}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md#concept_957D9E1977774D28A98ACEE6035E7B37) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. This allows you, for example, to frequency cap the number of times a user is shown a particular creative, within a media campaign. Other use cases include:

### Retarget Users

Retarget users who saw creative 123 but didn't click or convert and show them creative 456. Do this:

1. Create a trait to capture users who saw the creative. Let's say you name the trait [!DNL Creative Trait 123]. Use the trait rule:

   `d_creative == 123 AND d_event == imp`

1. Create a trait to capture users who click or convert. Let's say you name this one [!DNL Click and Converter]. Use the trait rule:

   `d_event == click OR d_event=conv`

1. Create a segment to populate with users who saw creative 123 but didn't click or convert. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Use [!DNL DCM] [!UICONTROL Floodlight Activity] in the [!UICONTROL Audience Optimization Reports] or in [!UICONTROL Audience Lab]

[Floodlight tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) enable advertisers to track user conversions. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md#concept_D66D2C58493E48BDAFF2F95BBB508946) or in [Audience Lab](../../features/audience-lab/audience-lab.md#concept_CEAEE1C751CE405DB99041FC57CC17E0):

1. Create a trait and use the following trait rule to capture a conversion from the ad server logs:

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_LIKE_THIS]
>
>* [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md#task_5BBF62BBAA7D43AFA6DCCF53C6DBEF00)
>* [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md#concept_D66D2C58493E48BDAFF2F95BBB508946)
