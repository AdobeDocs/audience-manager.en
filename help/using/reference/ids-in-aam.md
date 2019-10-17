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

Refer to this document for the complete list of Adobe Audience Manager IDs.

| ID | Name and Description | Example |
|---|---|---|
| [!DNL AAM UUID] | Audience Manager Unique User ID. A numerical, 38-digit device ID that Audience Manager associates to each device it interacts with. Think of this ID whenever you see a mention of unique users in the Audience Manager UI. Audience Manager saves this ID as a cookie in the `demdex.net` 3rd party domain. The Audience Manager UUID is sent in event calls as the `d_uuid` signal. | `demdex = 07955261652886032950143702505894272138` |
| [!DNL ImsOrgId]|Organization ID. This is the ID that a company is provided with upon signing up for the Experience Cloud. To learn how you can find your company's Organization ID, read [Find your Organization ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |`5DC5123F5245B1D20A490D46@AdobeOrg`|
|PID|Partner ID. The PID is a company's ID in Audience Manager. Audience Manager associates an [!DNL imsOrgId] to a [!DNL PID]. |`1352`|
|[!DNL ECID], [!DNL MID]|Experience Cloud ID. The Experience Cloud ID ([!DNL ECID], legacy abbreviations [!DNL MID] or [!DNL MCID]) is derived mathematically from your Organization ID and the Audience Manager Unique User ID. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. You can read more about the ECID in the [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) documentation. |`mid = 08382830887934830189014177072406221371` |
|[!DNL SID]|Trait ID. The Trait ID uniquely identifies traits in the Audience Manager environment. A Trait ID is assigned to each trait in the user interface (UI). |`289983`|
|SID|Segment ID. The Segment ID uniquely identifies segments in the Audience Manager environment. A Segment ID is assigned to each segment in the UI. |`4798574`|
|[!DNL csegID]|Legacy Segment ID. This ID uniquely identifies segments in the Audience Manager environment. A Legacy Segment ID is assigned to each segment in the UI. |`741232`|
|[!DNL destID]|Destination ID. The Destination ID uniquely identifies destinations in the Audience Manager environment. An ID is assigned to each destination in the UI. |`2523`|
|[!DNL DPID]|Data Source ID (also referred to as Data Provider ID). The Data Source ID is a namespace for IDs or traits. An ID is assigned to each data source (data provider) in the UI. | `39217` |
|[!DNL DPUUID]|Data Provider Unique User ID (also referred to as [!DNL CRM ID]). A third-party ID. This is the ID by which you identify end users in your own [!DNL CRM] system. You can sync [!DNL DPUUIDs] with Audience Manager [!DNL UUIDs] and you can sync [!DNL DPUUIDs] from your different Data Sources ([!DNL DPIDs]) in the ID synchronization process. |`2132-3423vn-343fds-3432r`|
|[!DNL CRM ID]|See DPUUID.|`2132-3423vn-343fds-3432r`|
|[!DNL CID], [!DNL CID_IC]|Customer ID, Customer ID Integration Code. The [!DNL CID] and [!DNL CID_IC] key-value pairs replace [!DNL DPID] and [!DNL DPUUID]. They provide the same functions as the [!DNL DPID] and [!DNL DPUUID], but are more efficient because they include the data provider ID and user ID (or integration code) in a single key-value pair. ||
|[!DNL DAID]|Device Advertising ID. An ID unique to each hardware device, to be used for advertising purposes. Usually provided by the manufacturer of the device or device operating system. |See [Global Device IDs](#global-device-ids). |

## Global Device IDs {#global-device-ids}

Global device IDs are device advertising IDs, unique to each device, provided by the device manufacturer or the operating system. The table below explains what these IDs are and what their format is.

| ID  | Name and Description | Example                                                                       |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [!DNL IDFA]                                 | [!DNL Identifier for Advertisers] IDs are mobile device identifiers, provided by the device manufacturer. These IDs represent devices that run the iOS operating system.        | The format strictly consists of 32 uppercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters.<br> Example: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID]                                 | [!DNL Google Advertising ID]s are mobile device identifiers provided by Android device manufacturers. These IDs represent devices that run the [!DNL Android] operating system. | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA]                                 | [!DNL Roku IDs for Advertising] represent [!DNL Roku] streaming devices.                                                                                                        | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID]                                 | [!DNL Microsoft Advertising ID]s are device identifiers generated by [!DNL Windows 10] on a per-device, per-user basis.                                                         | [!DNL MAID]s are formatted as alphanumeric strings.                                                                                                                                                                        |
| [!DNL DUID]                                 | [!DNL Samsung DUID]s are device identifiers provided by Samsung Smart TVs.                                                                                                      | Samsung [!DNL DUID]s are formatted as alphanumeric strings.                                                                                                                                                                |
| [!DNL Amazon Fire TV Advertising ID] | Device identifiers representing devices runinng the [!DNL Fire OS] operating system.                                                                                            | The format strictly consists of 32 lowercase hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. <br>Example: `df07c7dc-cea7-4a89-b328-810ff5acb15d`  |
