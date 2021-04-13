---
description: Refer to this document for the complete list of Adobe Audience Manager IDs.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index of IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
---
# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Overview {#overview}

[!DNL Audience Manager] uses multiple IDs to identify and manage the data you send to it. Refer to this article for the complete list of [!DNL Audience Manager] IDs, together with examples of the prefixes you should use them with.

## ID Prefixing {#prefixing}

While you can refer to most of these IDs by their standalone names, most of them are meant to be used with various prefixes, when passing in data through [!DNL DCS] calls. Some of these IDs are used by [!DNL Audience Manager] without being exposed to users, while others are also visible in the user interface (UI).

To understand the prefixes used in the following examples, see [Supported Attributes for DCS API Calls](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] List of IDs {#id-list}

| ID | Name and Description | Usage and Examples | User Interface Location|
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], also known as [!UICONTROL Device ID]. A numerical, 38-digit device ID that [!DNL Audience Manager] associates to each device it interacts with. Think of this ID whenever you see a mention of unique users in the [!DNL Audience Manager] UI. Audience Manager saves this ID as a [!DNL cookie] in the `demdex.net` 3rd party domain. | In [!DNL DCS] calls, `uuid` is preceded by the `d_` prefix. <br>Example: `d_uuid = 07955261652886032950143702505894272138` |You can filter [!DNL traits] by [!UICONTROL Device ID] when creating [Look-Alike Models](../features/algorithmic-models/create-model.md), and [building segments](../features/segments/segment-builder.md). You can also filter results by [!UICONTROL Device ID] when running [General Reports for Traits](../reporting/general-reports.md) and [Trend Reports for Traits](../reporting/trend-reports.md).|
|[!DNL ImsOrgId]|[!DNL Organization ID]. This is the ID that a company is provided with upon signing up for an [!DNL Experience Cloud] account. |`5DC5123F5245B1D20A490D46@AdobeOrg`|Not visible in the [!DNL Audience Manager] user interface. To learn how you can find your company's [!DNL Organization ID], read [Find your Organization ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255).|
|[!DNL PID]|[!DNL Partner ID]. The [!DNL PID] is a company's ID in [!DNL Audience Manager]. Audience Manager associates an [!DNL imsOrgId] to a [!DNL PID]. |`1352`| Not visible in the [!DNL Audience Manager] user interface. |
|[!DNL ECID], [!DNL MID]|[!DNL Experience Cloud] ID. The [!DNL Experience Cloud] ID ([!DNL ECID], legacy abbreviations [!DNL MID] or [!DNL MCID]) is derived mathematically from your [!DNL Organization ID] and the [!DNL Audience Manager] [!UICONTROL Unique User ID]. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same [!DNL Organization ID] and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. You can read more about the [!DNL ECID] in the [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentation. |`mid = 08382830887934830189014177072406221371` | Not visible in the [!DNL Audience Manager] user interface.|
|[!DNL SID]|[!UICONTROL Trait ID]. The [!UICONTROL Trait ID] uniquely identifies [!DNL traits] in the [!DNL Audience Manager] environment. |In [!DNL DCS] calls, `SID` is preceded by the `d_` prefix. <br>Example `d_sid=289983`.|A [!UICONTROL Trait ID] is assigned to each [!DNL trait], and visible in the user interface, in the [Traits](../features/traits/trait-details-page.md) page.|
|[!DNL SID]|[!UICONTROL Segment ID]. The [!UICONTROL Segment ID] uniquely identifies [!DNL segments] in the [!DNL Audience Manager] environment. |In [!DNL DCS] calls, `SID` is preceded by the `d_` prefix. <br>Example `d_sid=4798574`.|A [!UICONTROL Segment ID] is assigned to each [!DNL segment], and visible in the user interface, in the [Segments](../features/segments/segment-summary-view.md) page.|
|[!DNL csegID]|[!DNL Legacy Segment ID]. This ID uniquely identifies segments in the [!DNL Audience Manager] environment. |`741232`| A [!UICONTROL Legacy Segment ID] is assigned to each segment, and visible in the user interface, in the [Segments](../features/segments/segment-summary-view.md) page.|
|[!DNL destID]|[!UICONTROL Destination ID]. The [!UICONTROL Destination ID] uniquely identifies [!DNL destinations] in the [!DNL Audience Manager] environment. An ID is assigned to each [!DNL destination] in the user interface. |`2523`|A [!UICONTROL Destination ID] is assigned to each [!DNL destination], and visible in the user interface, in the [Destinations](../features/destinations/destinations-home.md) page.|
|[!DNL DPID]|[!UICONTROL Data Source ID] (also referred to as [!UICONTROL Data Provider ID]). The [!UICONTROL Data Source ID] is a namespace for IDs or [!DNL traits]. An ID is assigned to each [!DNL data source] (data provider) in the user interface. | In [!DNL DCS] calls, `dpid` is preceded by the `d_` prefix. <br>Example: `d_dpid=39217`.| A [!UICONTROL Data Provider ID] is assigned to each [!DNL data source], and visible in the user interface, in the [Data Sources](../features/datasources-list-and-settings.md) page.|
|[!DNL DPUUID]|[!UICONTROL Data Provider Unique User ID], also referred to as [!DNL CRM ID] or [!UICONTROL Cross-Device ID]. A third-party ID. This is the ID by which you identify end users in your own [!DNL CRM] system. You can sync [!DNL DPUUIDs] with [!DNL Audience Manager] [!DNL UUIDs] and you can sync [!DNL DPUUIDs] from your different [!UICONTROL Data Sources] ([!DNL DPIDs]) in the ID synchronization process. | In [!DNL DCS] callls, `dpuuid` is preceded by the `d_` prefix. <br> Example `d_dpuuid=2132-3423vn-343fds-3432r`.|You can filter [!DNL traits] by [!UICONTROL Cross-Device ID] when creating [Look-Alike Models](../features/algorithmic-models/create-model.md), and [building segments](../features/segments/segment-builder.md). You can also filter results by [!UICONTROL Cross-Device ID] when running [General Reports for Traits](../reporting/general-reports.md) and [Trend Reports for Traits](../reporting/trend-reports.md).|
|[!DNL CRM ID]|See `DPUUID`.|See `DPUUID`.|See `DPUUID`.|
|[!DNL CID], [!DNL CID_IC]|[!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. The [!DNL CID] and [!DNL CID_IC] key-value pairs replace [!DNL DPID] and [!DNL DPUUID]. They provide the same functions as the [!DNL DPID] and [!DNL DPUUID], but are more efficient because they include the data provider ID and user ID (or integration code) in a single key-value pair. |In [!DNL DCS] calls, these IDs are preceded by the `d_` prefix. <br>Example: `d_cid_ic=39217_myIntegrationCode`.| See `DPID` and `DPUUID`.|
|[!DNL DAID]|[!UICONTROL Device Advertising ID]. An ID unique to each hardware device, to be used for advertising purposes. Usually provided by the manufacturer of the device or device operating system. |See [Global Device IDs](#global-device-ids). ||

## [!DNL Global Device IDs] {#global-device-ids}

Global device IDs are device advertising IDs, unique to each device, provided by the device manufacturer or the operating system. The table below explains what these IDs are and what their format is. For more information about global device IDs and how to use them in [!DNL Audience Manager], read [Global Data Sources](/help/using/features/global-data-sources.md).

| ID  | [!DNL Global Data Source ID] | Name and Description | Example   |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915  | [!DNL Identifier for Advertisers] IDs are mobile device identifiers, provided by the device manufacturer. These IDs represent devices that run the [!DNL iOS] operating system.  | The format strictly consists of 32 uppercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters.<br> Example: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914  | [!DNL Google Advertising ID]s are mobile device identifiers provided by Android device manufacturers. These IDs represent devices that run the [!DNL Android] operating system. | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963  | [!DNL Roku IDs for Advertising] represent [!DNL Roku] streaming devices. | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s are device identifiers generated by [!DNL Windows 10] on a per-device, per-user basis.   | [!DNL MAID]s are formatted as alphanumeric strings. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] are device identifiers provided by [!DNL Samsung] Smart TVs.   | [!DNL Samsung] [!DNL TIFA] IDs are formatted as alphanumeric strings.  |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Device identifiers representing devices running the [!DNL Fire OS] operating system.    | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `df07c7dc-cea7-4a89-b328-810ff5acb15d`  |
