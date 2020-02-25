---
description: Refer to this document for the complete list of Adobe Audience Manager IDs.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index of IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
---

# Index of IDs in Audience Manager{#index-of-ids-in-audience-manager}

## Overview {#overview}

Audience Manager uses multiple IDs to identify and manage the data you send to it. Refer to this article for the complete list of Adobe Audience Manager IDs, together with examples of the prefixes you should use them with.

## ID Prefixing {#prefixing}

While you can refer to most of these IDs by their standalone names, most of them are meant to be used with various prefixes, when passing in data through DCS calls. Some of these IDs are used by Audience Manager without being exposed to users, while others are also visible in the user interface (UI).

To understand the prefixes used in the following examples, see [Supported Attributes for DCS API Calls](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Audience Manager List of IDs {#id-list}

| ID | Name and Description | Usage and Examples | UI Location|
|---|---|---|---|
| [!DNL AAM UUID] | Audience Manager Unique User ID. A numerical, 38-digit device ID that Audience Manager associates to each device it interacts with. Think of this ID whenever you see a mention of unique users in the Audience Manager UI. Audience Manager saves this ID as a cookie in the `demdex.net` 3rd party domain. | In [!DNL DCS] calls, `uuid` is preceded by the `d_` prefix. <p> `d_uuid = 07955261652886032950143702505894272138` </p> | Not visible in the Audience Manager UI.|
|[!DNL ImsOrgId]|Organization ID. This is the ID that a company is provided with upon signing up for an Experience Cloud account. |`5DC5123F5245B1D20A490D46@AdobeOrg`|Not visible in the Audience Manager UI. To learn how you can find your company's Organization ID, read [Find your Organization ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255).|
|PID|Partner ID. The PID is a company's ID in Audience Manager. Audience Manager associates an [!DNL imsOrgId] to a [!DNL PID]. |`1352`| Not visible in the Audience Manager UI. |
|[!DNL ECID], [!DNL MID]|Experience Cloud ID. The Experience Cloud ID ([!DNL ECID], legacy abbreviations [!DNL MID] or [!DNL MCID]) is derived mathematically from your Organization ID and the Audience Manager Unique User ID. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. You can read more about the ECID in the [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) documentation. |`mid = 08382830887934830189014177072406221371` | Not visible in the Audience Manager UI.|
|[!DNL SID]|Trait ID. The Trait ID uniquely identifies traits in the Audience Manager environment. |In [!DNL DCS] calls, `SID` is preceded by the `d_` prefix. <p>Example `d_sid=289983`</p>|A Trait ID is assigned to each trait, and visible in the UI, in the [!UICONTROL Traits] page.|
|[!DNL SID]|Segment ID. The Segment ID uniquely identifies segments in the Audience Manager environment. |In [!DNL DCS] calls, `SID` is preceded by the `d_` prefix. <p>Example `d_sid=4798574`</p>|A Segment ID is assigned to each segment, and visible in the UI, in the [!UICONTROL Segments] page.|
|[!DNL csegID]|Legacy Segment ID. This ID uniquely identifies segments in the Audience Manager environment. |`741232`| A Legacy Segment ID is assigned to each segment, and visible in the UI, in the [!UICONTROL Segments] page.|
|[!DNL destID]|Destination ID. The Destination ID uniquely identifies destinations in the Audience Manager environment. An ID is assigned to each destination in the UI. |`2523`|A Destination ID is assigned to each destination, and visible in the UI, in the [!UICONTROL Destinations] page.|
|[!DNL DPID]|Data Source ID (also referred to as Data Provider ID). The Data Source ID is a namespace for IDs or traits. An ID is assigned to each data source (data provider) in the UI. | In [!DNL DCS] calls, `dpid` is preceded by the `d_` prefix. <p>Example: `d_dpid=39217` </p>| A Data Provider ID is assigned to each data source, and visible in the UI, in the [!UICONTROL Data Sources] page.|
|[!DNL DPUUID]|Data Provider Unique User ID (also referred to as [!DNL CRM ID]). A third-party ID. This is the ID by which you identify end users in your own [!DNL CRM] system. You can sync [!DNL DPUUIDs] with Audience Manager [!DNL UUIDs] and you can sync [!DNL DPUUIDs] from your different Data Sources ([!DNL DPIDs]) in the ID synchronization process. | In DCS callls, `dpuuid` is preceded by the `d_` prefix. <p> Example `d_dpuuid=2132-3423vn-343fds-3432r` </p>|Not visible in the Audience Manager UI.|
|[!DNL CRM ID]|See `DPUUID`.|See `DPUUID`.|See `DPUUID`.|
|[!DNL CID], [!DNL CID_IC]|Customer ID, Customer ID Integration Code. The [!DNL CID] and [!DNL CID_IC] key-value pairs replace [!DNL DPID] and [!DNL DPUUID]. They provide the same functions as the [!DNL DPID] and [!DNL DPUUID], but are more efficient because they include the data provider ID and user ID (or integration code) in a single key-value pair. |In DCS calls, these IDs are preceded by the `d_` prefix. <p>Example: `d_cid_ic=39217_myIntegrationCode`</p>| See `DPID` and `DPUUID`.|
|[!DNL DAID]|Device Advertising ID. An ID unique to each hardware device, to be used for advertising purposes. Usually provided by the manufacturer of the device or device operating system. |See [Global Device IDs](#global-device-ids). ||

## Global Device IDs {#global-device-ids}

Global device IDs are device advertising IDs, unique to each device, provided by the device manufacturer or the operating system. The table below explains what these IDs are and what their format is. For more information about global device IDs and how to use them in Audience Manager, read [Global Data Sources](/help/using/features/global-data-sources.md).

| ID  | Global Data Source ID | Name and Description | Example   |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915  | [!DNL Identifier for Advertisers] IDs are mobile device identifiers, provided by the device manufacturer. These IDs represent devices that run the iOS operating system.  | The format strictly consists of 32 uppercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters.<br> Example: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914  | [!DNL Google Advertising ID]s are mobile device identifiers provided by Android device manufacturers. These IDs represent devices that run the [!DNL Android] operating system. | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963  | [!DNL Roku IDs for Advertising] represent [!DNL Roku] streaming devices. | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s are device identifiers generated by [!DNL Windows 10] on a per-device, per-user basis.   | [!DNL MAID]s are formatted as alphanumeric strings. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s are device identifiers provided by Samsung Smart TVs.   | Samsung [!DNL DUID]s are formatted as alphanumeric strings.  |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Device identifiers representing devices running the [!DNL Fire OS] operating system.    | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `df07c7dc-cea7-4a89-b328-810ff5acb15d`  |