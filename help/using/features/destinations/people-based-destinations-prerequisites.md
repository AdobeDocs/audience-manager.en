---
description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisites and Considerations
---

# Prerequisites and Considerations {#prerequisites-considerations}

Read below for an overview of customer requirements that you need to meet before signing up for [!DNL People-Based Destinations].

>[!IMPORTANT]
> Read through this article carefully before moving on to the implementation phase.

## Signing up for People-Based Destinations {#signing-up}

[!DNL People-Based Destinations] is a premium capability that enhances your Audience Manager experience by allowing you to activate first-party audience segments in people-based environments, by targeting your audience with customized offers on social networks or through email marketing.

Please contact your Adobe sales representative for details on how you can sign up for [!DNL People-Based Destinations].

## Partner-Specific Prerequisites {#partner-prerequisites}

### [!DNL Facebook]

Before you can use [!DNL People-Based Destinations] to send audience segments to [!DNL Facebook], make sure you meet the following requirements:

1. Your [!DNL Facebook] user account must have the **Manage campaigns** permission enabled for the Ad account that you plan to use.
1. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/708679622611131) for details.
    >[!IMPORTANT]
    > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. This is required for the [!DNL People-Based Destinations] integration.
1. Read and sign the [!DNL Facebook Custom Audiences] Terms of Service. To do this, go to `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, where `accountID` is your [!DNL Facebook Ad Account ID].

## Data Onboarding {#data-onboarding}

Data ingestion for [!DNL People-Based Destinations] currently supports up to 10 hashed email addresses linked to one customer ID ([!DNL CRM ID]), per batch transfer. Uploading more than 10 hashed email addresses linked to one customer ID causes Audience Manager to ingest 10 of them, in no specific order.

Uploading more than 10 hashed email addresses linked to one customer ID in multiple batch transfers causes Audience Manager to retain the most recent 10 email addresses added.

## Data Privacy {#data-privacy}

Although [!DNL People-Based Destinations] allow you to target audiences based on email addresses, no directly identifiable visitor information ever reaches Audience Manager. In the data onboarding phase, you must ensure that the email addresses you plan to use are hashed with the [!DNL SHA256] algorithm. Otherwise, you won't be able to use them in [!DNL People-Based Destinations].

## Data Hashing Versus Encryption {#data-hashing-encryption}

Encryption is a two-way function. Any encrypted information can also be decrypted, using the correct decryption key. Encrypting data in the context of Audience Manager poses a serious privacy risk, since any encrypted form of personally identifiable information can also be decrypted, revealing sensitive customer data. As opposed to encryption, [!DNL People-Based Destinations] are designed to work with hashed data instead, protecting the customer data that you use for targeting.

Hashing is a one-way function that scrambles the input to produce a unique result. By using proper hashing algorithms, like [!DNL SHA256], there is no way to reverse the hashing function and reveal the unscrambled information. The email addresses that you will onboard to Audience Manager must be hashed with the [!DNL SHA256] algorithm. This way, no personally identifiable information ever reaches Audience Manager, keeping your customer data safe.

## Hashing Requirements {#hashing-requirements}

When hashing the email addresses, make sure to comply with the following requirements:

* Trim all leading and trailing spaces from the email string; example: `johndoe@example.com`, not `<space>johndoe@example.com<space>`;
* Make sure the hashed string is all lowercase; example: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Do not salt the string.

Adobe Experience Cloud gives you the option to hash customer IDs through the Experience Cloud ID Service. See [SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) for detailed information on how to use ECID to hash customer IDs.

## Obtaining User Permission {#obtaining-user-permission}

Since [!DNL People-Based Destinations] helps you activate first-party audience data in people-based channels, it is your responsibility to inform your customers of how you will use their data for advertising purposes.

Before you sign up for [!DNL People-Based Destinations], make sure to obtain your customers' consent before using their information for advertising purposes.

In case your customers wish to opt-out of advertising campaigns, see [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md) for details on how to stop Audience Manager from collecting data any further.

## Enforcing First-Party Data Activation {#enforcing-first-party-activation}

When using [!DNL People-Based Destinations], you can only use first-party data to activate audience segments in people-based channels. You cannot use any second- or third-party data for audience activation in people-based channels.

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

There are two ways you can bring your offline data to Audience Manager for [!DNL People-Based Destinations].

* [Send batch data](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) to Audience Manager to ingest hashed email addresses. With this method, you can use all of the hashed email addresses from your [!DNL CRM] database in [!DNL People-Based Destinations]. Additionally, when using this method, you can also qualify the hashed email addresses for [onboarded traits](../traits/trait-qualification-reference.md).
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager only sends to [!DNL People-Based Destinations] the hashed email addresses from users who have authenticated online. The email addresses activated through Facebook are only the ones in the declared ID event calls. Other email addresses associated with the customer ID are not sent in real-time.
