---
description: Answers to common questions about People-Based Destinations.  
seo-description: Answers to common questions about People-Based Destinations.  
seo-title: People-Based Destinations FAQ
solution: Audience Manager
title: People-Based Destinations FAQ
---

# People-Based Destinations FAQ {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability

**I cannot see [!DNL People-Based Destinations] in my Audience Manager account. What do I need to know about availability?**

[!DNL People-Based Destinations] is a premium Audience Manager feature that is available upon purchase. Please contact your Adobe sales representative for details about pricing and availability.

## Data Onboarding

**How can I onboard customer email addresses into Audience Manager, so that I can use them in [!DNL People-Based Destinations]?**

There are two ways you can bring your offline data to Audience Manager for [!DNL People-Based Destinations].

* **Use file-based ID synchronization**. See [Name and Content Requirements for ID Synchronization Files]() for details on what ID synchronization files should look like. When using this method, you can target all of the hashed email addresses from your [!DNL CRM] database.
* **Use Declared IDs** to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager only activates the hashed email addresses from users who have authenticated online. The email addresses activated through Facebook are only the ones in the declared ID event calls. Other email addresses associated with the customer ID are not activated in real-time.

**Can I collect hashed email addresses through a web form or mobile app or do they have to come through on a batch file?**

You can collect hashed email addresses through web authentication using [!DNL ECID] with [Declared IDs](../declared-ids.md). The batch file allows you to also collect hashed email addresses that can’t be sent through authentication (e.g. dormant users in your ([!DNL CRM]) and activate them in people-based destinations.

**How is ingesting hashed email addresses via web forms different from uploading hashed email addresses via batch files?**

Offline data ingestion is designed to support use cases without authentication, and a new profile merge rule ([!UICONTROL All Cross-Device Profiles]) that runs on all of the offline [!DNL CRM] profiles irrespective of authentication is available as part of [!DNL People-Based Destinations]. This method is meant to complement the ingestion of authenticated audiences from online sources.

**What is the maximum frequency at which I can send/update hashed email addresses?​**

* When using Declared IDs, Audience Manager sends the hashed email addresses to the destination in real time.
* When ingesting data through ID synchronization files, Audience Manager processes them on a daily basis.

**How do I know if the email address hashing is done correctly?**

Audience Manager is not ingesting the raw email address and we cannot validate that the hash was done correctly. See [Prerequisites and Considerations](people-based-destinations-prerequisites.md) for details on how you should hash the onboarded data.

## Profile Merge Rules

**Is there a new profile merge rule that I can use with [!DNL People-Based Destinations]?**

Yes. Customers who purchase [!DNL People-Based Destinations] are also granted access to a new profile merge rule for offline segmentation. The rule is called [!DNL All Cross-Device Profiles] and it is used for offline-only segmentation. When you sign up for [!DNL People-Based Destinations], this is the fourth profile merge rule that you can create, aside from the three existing authentication-based rules.

**Do I have to duplicate my existing audience segments to activate them in [!DNL People-Based Destinations]?**

It depends on your use case. If you plan on activating existing first-party segments in people-based channels, you don't need to create new segments. You can just map the segments to a people-based destination.

If you plan on activating new offline audiences in people-based channels, you need to create new first-party segments using the [!DNL All Cross-Device Profiles] merge rule.
>[!NOTE]
> 
> You can only map segments with first-party data to [!DNL People-Based Destinations]. Our destination platforms do not accept segments with second- and third-party data.

## Match Rates

**Do [!DNL People-Based Destinations] have visibility into match rates or addressable audiences?**

No. When sending audience segments to [!DNL People-Based Destinations], audience matching happens on the partner side. Adobe does not have access to those metrics. Audience Manager shows you the maximum shareable audience for each destination and the real-time count of people belonging to a segment. This information can help you with campaign planning and forecasting.

**How would match rates using [!DNL People-Based Destinations] theoretically compare to other methods of sending audiences to destination platforms?**

As long as the email address is hashed and ingested correctly, there should be no difference in the match rate between [!DNL People-Based Destinations] and other methods. The only reason a match rate would be below 100% is if the email addresses brought into Audience Manager cannot be matched with an email address in the destination platform’s user base.

**I collect work email addresses from my customers, which are different from the personal email addresses used in social networks. How do you match identities across multiple email addresses?**

Audience Manager can collect and send up to 10 emails per user to destination platforms, but the email addresses need to be captured through synchronization files. After Audience Manager sends the email addresses to destination platforms, it is up to the platforms to match the email addresses against their own user base. Some platforms may have additional email address graphs to match addresses sent from Audience Manager to user profiles.

## Data Export Controls

**How do [!DNL Data Export Controls] work with [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] will block any segments containing second- and third-party data that users attempt to send to [!DNL People-Based Destinations]. [!DNL People-Based Destinations] only allow first-party data to be used for targeting. [!DNL Data Export Controls] also block segments using [!DNL Profile Merge Rules] with device graphs. [!DNL People-Based Destinations] are created with the appropriate data export labels checked and you cannot overwrite the export settings.

## Partner Specific Questions

### [!DNL Facebook]

**What do I need to do before I can send audience segments to [!DNL Facebook]?**

Before you can use [!DNL People-Based Destinations] to send audience segments to [!DNL Facebook], you need to perform the following configuration tasks:

1. Add the Adobe Experience Cloud business account as an advertising partner in your [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. See Add Partners to Your Business Manager for details.
    
    >[!IMPORTANT]
    >
    > When configuring the permissions for Adobe Experience Cloud, you must enable the Manage campaigns permission. This is required for the [!DNL People-Based Destinations] integration.
 
1. Read and sign the [!DNL Facebook Custom Audiences Terms of Service]. To do this, go to `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, where `accountID` is your [!DNL Facebook Ad Account ID].

**Do [!DNL People-Based Destinations] support audience targeting in other [!DNL Facebook] apps, such as [!DNL Instagram]?**

You can use [!DNL People-Based Destinations] across [!DNL Facebook]’s family of apps that are supported by [!DNL Custom Audiences], including [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] and [!DNL Messenger]. Selection of the app that you want to run campaign against is indicated at the placement level in [!DNL Facebook Ads Manager].

**What’s the difference between [!DNL People-Based Destinations] and [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] leverages the [!DNL Custom Audiences (CA)] integration with [!DNL Facebook]. The difference between [!DNL WCA] and [!DNL CA] integrations is the key that customers use when sending audiences to [!DNL Facebook]. [!DNL WCA] uses the [!DNL Facebook] pixel (which would be a website user ID) while [!DNL People-Based Destinations] use hashed email addresses to integrate with [!DNL CA].

You can use Audience Manager’s [!DNL Facebook] [!DNL WCA] integration via the [!DNL URL Destinations] feature at no extra cost.

These two integrations are complementary; you can use both to ensure better audience coverage. As an example, [!DNL WCA] can be used for prospecting when a company is looking to target website visitors who have not registered an account, whereas [!DNL People-Based Destinations] can help you target existing customers who have supplied their email address but maybe not visited the website.



