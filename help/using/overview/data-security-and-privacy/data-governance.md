---
description: This document explains how customer data is governed in Audience Manager.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Data Governance
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
---
# Data Governance

## Overview {#overview}

Data Governance in Audience Manager refers to the lifecycle of your customer data in Audience Manager, and it encompasses [Collecting and Obfuscating IP Addresses](data-governance.md#collecting-ip-addresses), [Data Retention](data-governance.md#data-retention), and [Cross-border Data Transfers](data-governance.md#data-transfers).

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**IP Obfuscation Methodology:** Following the principles of "Privacy By Design", Adobe Audience Manager allows customers to enable [!DNL IP] obfuscation from the UI, either globally across all geographic regions or for specific countries. When you enable this setting, the last octet (the last portion) of the [!DNL IP] address is immediately discarded when the [!DNL IP] address is ingested into Audience Manager. Audience Manager discards this part of the [!DNL IP] address prior to processing (including before any optional geographic lookup or logging of the [!DNL IP] address). For example:

* Before: `255.255.255.255`
* After: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](../../features/administration/ip-obfuscation.md) to learn how to enable [!DNL IP] address obfuscation in the Audience Manager user interface.

Watch the video below to understand how [!DNL IP] address obfuscation works in Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geographic Segmentation:** If you enable [!DNL IP] address obfuscation, the remaining octets of the [!DNL IP] address can still be used for geo-segmentation and reporting in Audience Manager. If you do not enable [!DNL IP] address obfuscation, Audience Manager uses the full [!DNL IP] address. You can use the Geographic Segmentation feature that allows you to identify an [!DNL IP] location by geographic area in either case, but with some slight loss of precision when [!DNL IP] obfuscation is being used. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. Obtaining region and country-level information should only be slightly impacted. Geographic Segmentation data is granular only to the city level or postal code level, and not to the individual level. Read more about [geo-targeting](../../features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Data Retention in Audience Manager {#data-retention}

Applying appropriate, secure, and timely data retention policies to your data is an important part of complying with data privacy regulations. Audience Manager Customers have the ability to set custom retention periods on traits and segments by defining the required TTL (time to live). See [Data Retention FAQ](../../faq/faq-privacy.md) for more details about retention periods.

## Cross-Border Data Transfers {#data-transfers}

When Audience Manager transfers personal data from Customers across national borders, Audience Manager does so in compliance with applicable law. Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.
