---
description: Common targeting-related questions and issues.
seo-description: Common targeting-related questions and issues.
seo-title: Targeting FAQ
solution: Audience Manager
title: Targeting FAQ
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
---

# Targeting FAQ{#targeting-faq}

Common targeting-related questions and issues.

<br>&nbsp;

<!-- 

faq_targeting.xml

 -->

**Where can I find a full list of third-party data providers supported by Audience Manager?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br>&nbsp;

**To target users I've never seen on my site with third-party data, should I use third-party data in Audience Manager or in a DSP?**

The answer depends on your goals. For example, if your campaign is designed to find new clients with third-party data, then work directly with a DSP. Remember, Audience Manager synchronizes data with a third-party data provider only when we see that user. If we have never seen a user before, our system will not have any information for that site visitor. For campaigns that only want to use third-party data to target users who have never visited any of your properties, then create those segments through the DSP.

<br>&nbsp;

**Can I market to individuals?**

Audience Manager lets you aggregate users and market to them based on shared attributes or traits. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. As a result, you cannot use email addresses, individual names, physical addresses, etc. for targeting.

<br>&nbsp;

**How do I keep retargeting data securely?**

We recommend you use a server-to-server connection to exchange data with your preferred retargeting platform. Audience Manager exchanges data with most of the major DSPs through server-to-server connections. Server-to-server data transfers help prevent other actors from intercepting your data and re-selling that audience information.

<br>&nbsp;

**Is the Audience Manager unique user ID (UUID) tied to an ad server's unique user ID by ID synching directly on the page?**

No. ID synchs are not made on the page for on-site publishers or servers. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. This happens as segment gets passed in for targeting. The DIL code module performs this function. This is the same mechanism that allows us to map the server's user ID to an Audience Manager user for segment performance reporting. However, if an ad server is present on site, then we synch IDs directly on the page.

<br>&nbsp;

**Does Audience Manager count a user who logs on from different devices as one unique user or different unique users?**

[Declared ID Targeting](../features/declared-ids.md#declared-id-targeting) helps Audience Manager identify a visitor across multiple devices with a single unique identifier. However, from a targeting or destination perspective, this is still 2 (or more) users because DSPs cannot reconcile those multiple IDs.

<br>&nbsp;

**Can Audience Manager identify a user from display and mobile devices.**

Yes. See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br>&nbsp;

**Can I score users with data collected online and retarget them based on this model score?**

Yes. Audience Manager can provide data files to help you score users, but you must work with other vendors or software to analyze and rank this information. Send this data to Audience Manager in the form of key-value pairs. We can take this information and append it to existing user profiles. Contact your Partner Solutions representative to review this process.

<br>&nbsp;

**What are the cookie deletion rates over a given 1 - 2 month period?**

Cookie deletion is difficult to measure. Most cookie deletion comes from a few visitors who delete cookies frequently. However, most browser cookies are stable for at least 30 days, even though some may have a limited life. Some studies suggest upper-funnel targeting that is greater than 30 days would effectively eliminate 7% of the browser target audience over a 30-day period. As you know, 30 day campaigns for a given creative message are standard in the industry. From what we’ve seen, that 7% drop-off is accurate.

Cookie deletion has an adverse effect on reach and frequency calculations. As a result, we stress the value of behavioral data when trying to understand the true nature of consumer trends for display campaign planning. Our clients can leverage Audience Manager segment overlap reports, optimal impression frequency reports, and unique user trends over specific date ranges to be more scientific about campaign planning and optimal date ranges for running campaigns.

<br>&nbsp;

**What is the expiration window for Audience Manager cookies?**

The user interface lets you determine the cookie expiration interval. You can set cookies to expire after *n* number of days or never.

<br>&nbsp;

**Does implementing a campaign creative in an event call cost us more?**

It depends. Cost is based on unique users. If a campaign results in net new users, then yes, this will cost more. If your campaign reaches places where we're already collecting data, then there's no additional cost. If your campaign runs on related sites where there is significant overlap, there will be additional cost for the new unique users we see.

<br>&nbsp;

**Audience Manager displays [!UICONTROL Addressable Audiences] metrics and match rates for [!UICONTROL Server-to-Server] destinations only. Can you explain why we don't see these figures for Cookie and URL destinations?**

It comes down to ID syncs. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. The segment addressable number is a subset of the total segment population.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. The destination partner can just pick up the segment mappings and work with that information. So consider the match rates for Cookie and URL destinations always 100%.
