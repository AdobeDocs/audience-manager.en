---
description: This document explains how consent management works in Audience Manager.
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Consent Management
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
TQID: https://experienceleague.adobe.com/ky1cNyZ507tDn2FFS6umoWsT-zaZ05wQwvK8xvNc7HU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
    internal-label: Audience Marketplace
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Consent Management

## Overview {#overview}

In instances where consent is needed for certain marketing activities, Audience Manager customers must determine the scope and, and whether certain consents need to be refreshed to be able to continue using data going forward.

Audience Manager offers you tools to help support your ability to obtain the required consents from your users, so that you can deliver personalized experiences to them across channels.

>[!IMPORTANT]
>
> The contents of this document are not legal advice and are not meant to substitute for legal advice.
>
> As your data processor, Adobe is not able to provide legal advice on obtaining consent. You may also want to consider working with a consent management solution provider, such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), and consult your company's legal department for advice concerning consent and practices when setting up your opt-in implementation.

## Experience Cloud Opt-in Service

The [Experience Cloud Opt-in Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

The [Experience Cloud Opt-in Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) also lets you set protocols to integrate with your Consent Management Platform (CMP) and existing systems as part of your larger design.

## Managing Opt-In / Obtaining Consent

Audience Manager customers have the ability to store user consent for various use cases such as advertising or personalization as traits in Audience Manager. Segments you build with these traits will then include only users providing the respective consent for each of these use cases. Please note that using this approach does not stop data collection but will only impact data usage when you send segments for activation. When users withdraw their consent, you can remove these traits from the user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

## Managing Opt-Out / Withdrawal of Consent

Opt-out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. 1-click features let your end users control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html) and [iOS devices](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html). You can find additional details for opt-out in the [Data Privacy Requests Documentation](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Managing Consent for Second Party Partners

Second Party Partners are generally also Data Controllers and own the process for obtaining any needed consent from the Data Subject to share data with their second party data partners. It is your responsibility, as an Audience Manager Customer, to determine if the Second Party Partner has obtained the necessary consent for your use case. More details on obtaining consent is covered above.

## Managing Consent for Audience Marketplace Third Party Partners

Audience Marketplace Third Party Partners are also Data Controllers and own their process for obtaining consent and managing access/delete/correction requests. Adobe is proactively requesting that Audience Marketplace Third Party Partners update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. Information will be sourced from the Audience Marketplace Third Party Partners and is updated on a regular basis. However, it is up to each Audience Manager Customer to determine that the Audience Marketplace Third Party Partner has obtained the necessary consent for that customer’s use case. Adobe makes no representations about the scope or validity of the consent obtained or reported by an Audience Marketplace Third Party Partner for a given use case.
