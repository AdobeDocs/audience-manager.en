---
description: This document explains how consent management works in Audience Manager.
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Consent Management
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
---

# Consent Management

## Managing Opt-In / Obtaining Consent

GDPR doesn’t change when Data Controllers need consent, it changes how to get consent. In those instances where consent is needed for certain marketing activities, consumer consent needs to be active (e.g., no pre-checked boxes or silence as assent), unbundled, and offers of services may not be made conditional upon the Data Subject giving consent. There may even be instances where certain consents need to be refreshed to be able to continue using data going forward.

As your data processor, Adobe is not able to provide legal advice on obtaining consent. Consult your legal team for guidance. We recommend that you work with a consent management solution providers such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) to provide better recommendations on this. Adobe has partnered with several such providers to assist with this integration via Adobe Launch.

Audience Manager customers could store user consent for various use cases such as advertising or personalization as traits in Audience Manager. Building segments with these traits will then include only users providing the respective consent for each of these use cases. Please note that using this approach does not stop data collection but will only impact data usage when you send segments for activation. When users withdraw their consent, you can remove these traits from user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

## Managing Opt-Out / Withdrawal of Consent

Opt out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. 1-click features let your end users control and opt out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) and [iOS devices](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). You can find additional details for opt-out in the [Audience Manager Opt-Out Documentation](../../overview/data-security-and-privacy/opt-out-management.md).

<br>&nbsp;

## Second Party Data Providers & Managing Consent

Second Party Data Providers are generally also Data Controllers and own the process for obtaining any needed consent from the Data Subject to share data with their second party data partners. It is the responsibility of the Audience Manager Customer to determine if the Second Party Data Provider has obtained the necessary consent for your use case. More details on obtaining consent is covered above.

## Third Party Data Providers & Managing Consent

Data Providers are also Data Controllers and own their process for obtaining consent and managing access/delete/correction requests. Adobe is proactively requesting that Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. Information will be sourced from the Data Providers and the goal is to have the tool updated by Q2 2018. However, it is up to each Audience Manager Customer to determine that the Third Party Data Provider has obtained the necessary consent for that customer’s use case. Adobe makes no representations about the scope or validity of the consent obtained or reported by a Third Party Data Provider for a given use case.

**Impact of Delete Requests for Audience Activation**

Audience Manager notifies activation partners about deletion requests by sending them unsegment information for Data Subjects requesting deletion of certain data. However, some activation partners: 1) cannot support unsegment (or remove segment) requests from Adobe and/or 2) are not able to receive updates from us with a frequency of less than 30 days. In those cases, Audience Manager Customers are not able to send delete requests to activation partners in an automated way through Audience Manager. The [GDPR Partner Unsegment documentation](aam-gdpr-partners.md) provides information about unsegment capabilities and frequency of data exchange for all activation partners.

<br>&nbsp;

## Data Retention in Audience Manager

Applying appropriate, secure, and timely data retention policies to your data is an important part of complying with GDPR. Audience Manager Customers have the ability to set custom retention periods on traits and segments by defining the required TTL (time to live). We have reduced the retention period for [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) and [!UICONTROL Batch Outbound] orders to 8 days. We will also be applying a retention period for inactive CRM profiles and ID mappings. Please find the more details about retention periods in our [Data Retention FAQ](../../faq/faq-privacy.md).

<br>&nbsp;

**Cross-Border Data Transfers**

GDPR doesn’t prohibit transfer of data outside of Europe. It requires that the privacy protections on European data persist wherever the data is transferred. Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.

<br>&nbsp;