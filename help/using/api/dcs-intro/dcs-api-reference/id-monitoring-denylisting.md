---
description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
keywords: id;monitoring;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID Monitoring and Denylisting
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
---

# ID Monitoring and Denylisting

The [!DNL DCS] monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.

## Overview

To protect the Audience Manager infrastructure against malicious activity, the [!DNL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!DNL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!DNL DCS] detects an unusually large amount of [!DNL DCS] requests for any given ID in a short amount of time, that ID is added to a deny list.

## Error Codes

You can identify IDs added to a deny list by the error codes received from the [!DNL DCS]. The error codes that you may receive are:

* 303: Blocked customer ID;
* 306: Blocked declared device ID;
* 307: Blocked profile operation for ID.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## Removing IDs from deny lists

IDs that have been added to deny lists should not be used in any future requests, since they will lead to incorrect data reporting. The [!DNL DCS] does not support the removal of IDs from deny lists.

## Impact on ID Synchronization

[!DNL DCS] calls can include one or multiple types of IDs. Calls containing a single ID are completely disregarded if that ID is added to a deny list, and no ID synchronization occurs in this situation.

When a multiple ID call also includes a denylisted ID, the [!DNL DCS] disregards the denied ID and only uses the remaining, allowed IDs for synchronization.

## Causes and Fixes for ID Denylisting

The most frequent cause of IDs being added to deny lists is the incorrect integration between customer infrastructure and Audience Manager. When you identify a denylisted ID, make sure to thoroughly review your Audience Manager integrations. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of IDs being added to deny lists are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!DNL DCS] multiple times. If you identify indexing bots as the reason for IDs being added to deny lists, you should restrict bot access to your website.

If you have a hard time identifying integration issues, don't hesitate to contact Customer Support. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. This archive helps the support team identify why the ID was added to a deny list.