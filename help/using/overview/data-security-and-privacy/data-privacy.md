---
description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Data Privacy Overview
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
---

# Data Privacy Overview {#data-privacy}

This article describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

## Data Privacy {#data-privacy-center}

Audience Manager recognizes the implicit pact between consumers and the online brands with which they interact. Both parties benefit from the transparent exchange of anonymous data elements:

* Consumers receive personalized content, discounted product offers, and streamlined user experiences.
* Brands receive vital revenue streams supporting multiple online business models.

In our continuing support of this model, Audience Manager remains committed to providing transparency and control to consumers, and meeting or exceeding the Online Behavioral Advertising (OBA) Self-Regulatory Principles.

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html) for more details.

Adobe ensures the Audience Manager privacy regulations compliance through the [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html).

This service provides a [!DNL RESTful API] and user interface to help you manage customer data requests. Using the [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), you can submit requests to access and delete private or personal customer data, facilitating automated compliance with organizational and legal privacy regulations.

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**IP Obfuscation Methodology:** Following the principles of "Privacy By Design", Adobe Audience Manager allows customers to enable [!DNL IP] obfuscation from the UI, either globally across all geographic regions or for specific countries. When you enable this setting, the last octet (the last portion) of the [!DNL IP] address is immediately discarded when the [!DNL IP] address is ingested into Audience Manager. Audience Manager discards this part of the [!DNL IP] address prior to processing (including before any optional geographic lookup or logging of the [!DNL IP] address). For example:

* Before: `255.255.255.255`
* After: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable [!DNL IP] address obfuscation in the Audience Manager UI.

Watch the video below to understand how [!DNL IP] address obfuscation works in Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geographic Segmentation:** If you enable [!DNL IP] address obfuscation, the remaining octets of the [!DNL IP] address can still be used for geo-segmentation and reporting in Audience Manager. If you do not enable [!DNL IP] address obfuscation, Audience Manager uses the full [!DNL IP] address. You can use the Geographic Segmentation feature that allows you to identify an [!DNL IP] location by geographic area in either case, but with some slight loss of precision when [!DNL IP] obfuscation is being used. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. Obtaining region and country-level information should only be slightly impacted. Geographic Segmentation data is granular only to the city level or postal code level, and not to the individual level. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Related concepts {#related-concepts}

* [Opt-out Management](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Privacy and Data Retention FAQ](/help/using/faq/faq-privacy.md)