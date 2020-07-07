---
description: The Marketplace is where data buyers go to research and subscribe to public and private data feeds. Follow these steps to subscribe to a public data feed.
seo-description: The Marketplace is where data buyers go to research and subscribe to public and private data feeds. Follow these steps to subscribe to a public data feed.
seo-title: Manage Data Feed Subscriptions
solution: Audience Manager
title: Manage Data Feed Subscriptions
topic: DIL API
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
---

# Manage Data Feed Subscriptions {#manage-data-feed-subscriptions}

The [!UICONTROL Marketplace] is where data buyers go to research and subscribe to public and private data feeds. Follow these steps to subscribe to a public data feed.

## Subscribe to a Public Data Feed {#subscript-public-data-feed}

The [!UICONTROL Marketplace] is where data buyers go to research and subscribe to public and private data feeds. Follow these steps to subscribe to a public data feed.

<!-- t_subscribe_feed.xml -->

To subscribe to a public data feed:

1. Go to **[!UICONTROL Audience Marketplace > Marketplace]**. Use the search feature or browse through the list to find a data feed.

   ![subscribe](assets/subscribe1.png)

1. Click the name of the data feed you want to use. This opens the [plan details page](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) for the selected feed.

   ![plan-details](assets/plan-details.png)

1. Choose a use case from the subscriptions table and:
    * Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL On]**.
    * Click **[!UICONTROL Review & Subscribe]**. This opens the [!UICONTROL Terms and Conditions] window.

   ![subscribe](assets/subscribe3.png)

1. In the [!UICONTROL Terms and Conditions] window:

    * **Important:** Leave the **[!UICONTROL ID sync]** check box checked. This setting helps improve match rates with your data provider.
    * Check the terms and conditions box and click **[!UICONTROL Accept]** to complete the subscription process.

   ![subscribe](assets/subscribe4.png)

### Next Steps

After you subscribe to a data feed:

* Verify the subscription by checking your [!UICONTROL Traits] folder. See [Storage for Subscribed Data Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

* Review the billing and payment documentation. See the related links below.

### Best Practices {#best-practices}

Here is a set of best practices that we recommend you follow when working with [!UICONTROL Audience Marketplace]:

When exploring new third and second-party data sets through [!UICONTROL Audience Marketplace], the first step we recommend is to enable data feeds for [!UICONTROL Segments & Overlap]. This allows users to explore data by building segments to evaluate audience size, and running overlap reports to gain initial audience insights. Most data providers offer this use case for free, so you can perform this analysis at no extra cost.

When running overlap reports, follow these best practices to make sure you're getting useful results.

1. Ensure that your overlapping data sets are similar in terms of data type and collection methodologies, such as:
   * Visitor geography
   * Cookie vs. Mobile IDs
   * Lookback window
   * Offline vs. Online activity
   * The frequency at which the data provider refreshes the data

1. Overlap can grow slightly over time, so make sure you allow up to 30 days to pass before running overlap reports to allow for the data to sync.
1. Overlap can increase if you use data from a data provider in multiple marketing campaigns.
and initiatives. This allows for more opportunities for users from the two data sets to sync.
1. There is no guarantee that there will be an overlap between your data sets. For an overlap to be valid, a user from the customer’s data set must be associated with the data
provider data set during the reporting time frame. If the customer’s media data didn’t get served to the users in the data provider data set, there will never be an overlap.
1. Don't think of low overlap as a bad thing. Take advantage of a low overlap to prospect and engage new users.

## Subscribe to a Private Data Feed {#subscript-private-data-feed}

Buyers subscribe to private data feeds and plans in **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_private_feed.xml -->

>[!TIP]
>
>Sometimes data providers may offer a discount on a private data feed. You might want to ask about a possible discount when submitting your subscription request.

To subscribe to a private data feed:

1. Click the data feed name in the [!UICONTROL Marketplace].
1. Click **[!UICONTROL Request Access]**. This opens the request dialog box.
1. In the request dialog box, write the provider a note expressing your interest in their data feed and click **[!UICONTROL Send]**. The seller will review your message and approve or reject your request. While waiting for approval, "Requested" appears in the [!UICONTROL Marketplace] list for that data feed.

    * **[!UICONTROL Request approved]**: The status in the [!UICONTROL Marketplace] list changes to "Access Granted" and you'll receive an automated notification. At this point you can subscribe to the feed. See [Subscribe to a Public Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed) for instructions.
    * **[!UICONTROL Request denied]**: The "Requested" text is removed from the [!UICONTROL Marketplace] list for the feed. You can try to subscribe again or choose a different feed.

## Data Feed Discounts for Buyers {#buyer-discount}

In [!UICONTROL Audience Marketplace], providers can offer buyers a discount on the published price of a [!DNL CPM] or flat rate data feed. However, discount amounts aren't visible to buyers in the [!DNL Marketplace] feed list. But, you can also ask for a discount when you subscribe to a private data feed or when requesting more information about a particular feed.

## Request a Discount {#request-discount}

<!-- marketplace-buyer-discounts.xml -->

<table id="table_3C6E58F593BA48EC89ACBD9A26E4E74F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Buyer Status </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Current Subscribers</b> </p> </td> 
   <td colname="col2"> <p>If you're already subscribed to a private data feed and want to request a discount: </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> Unsubscribe</a> from the data feed. </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">Contact the data provider and request a discounted price. </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">If the provider gives you a discount, re-subscribe to the feed on the 1<sup>st</sup> day of the next month. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>New Private Data Feed Subscribers</b> </p> </td> 
   <td colname="col2"> <p>Ask for a discount in your subscription request. See <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed"> Subscribe to a Private Data Feed</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Potential Subscribers</b> </p> </td> 
   <td colname="col2"> <p>A <a href="../../../features/audience-marketplace/marketplace-private-feeds.md"> potential subscriber</a> is a data buyer who has requested access to a private data feed, received seller approval, but has not subscribed to the feed. To request a discount as a potential subscriber: </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A">Go to <b><span class="uicontrol"> Audience Marketplace &gt; Marketplace</span></b>. </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">Click the name of the feed you've been approved for. </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540">Click <b><span class="uicontrol"> Request More Details</span></b>. Ask for a discount in your details request to the seller. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Review Discounted Feeds {#review-discounted-feeds}

To review your discounted feeds:

1. Go to **[!UICONTROL Audience Marketplace > Marketplace]**.
1. Click the name of a feed you're already subscribed to.
1. Look at the [!UICONTROL Price] and [!UICONTROL Your Price] columns in the [!UICONTROL Plan Details] table. If the feed is discounted:

    * The original price is marked with a red line.
    * The fee in the [!UICONTROL Your Price] column will be lower than the fee in the [!UICONTROL Price] column.

In the example, the buyer gets a 10% discount on the [!UICONTROL Segments and Overlap] plan in the **[!UICONTROL Software Audience Feed]**.

![](assets/buyer-discount.png)

## Finding Subscribed Feed Data {#find-subscribed-data-fee}

The data (traits) for your data feeds appears in their own trait storage folders. Go to **[!UICONTROL Audience Data > Traits]** and expand the **[!UICONTROL 3rd-Party Data]** folder to view and work with the traits in your subscribed feeds. Look for the sub-folder named after your data provider. Those contain folders named after the individual data feed and list traits provided by the feed.

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## Unsubscribe from a Data Feed {#unsubscribe}

Data buyers unsubscribe from data feeds and plans in **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_unsubscribe_feed.xml -->

To unsubscribe from a data feed:

1. Click the data feed name in the [!UICONTROL Marketplace].
1. In the [!UICONTROL Use Case] section find the plan you want to use and move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**.

## Data Feed Deactivation: Why It Happens and How to Respond {#data-feed-deactivation-reasons}

In [!UICONTROL Audience Marketplace], data providers can revoke access to your subscribed data feeds. Don't be alarmed if this happens to you. We've got you covered. Review this section for processes and procedures related to data feed deactivations.

## Common Reasons for Data Feed Deactivation {#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

It may be puzzling or even upsetting if a feed you subscribe to is shut off. However, data providers can deactivate a data feed for a variety of reasons. Some common reasons include:

* **Billing:** Data providers will deactivate a feed if you're consistently late with fee payments or if you fail to pay your fees.
* **Feed Updates:** Data providers need to deactivate feeds when they update their feed taxonomy or cost structures.
* **Inactive Buyers:** Data providers reserve the right to deactivate feeds if subscribers show no spending over an extended period of time.
* **Inactive Sellers:** Data providers who leave [!UICONTROL Audience Marketplace] will deactivate and delete all their data feeds.

>[!TIP]
>
>Contact your data provider directly if you believe a data feed was deactivated by mistake. Your [!DNL Adobe] consultant can help you with contact information or additional support.

## Deactivation Email {#deactivation-email}

When a data provider deactivates one of your data feeds, [!DNL Audience Manager] sends an email to the users in your company who have [!UICONTROL Administrator] permissions. Sometimes email filters classify this message as spam. As a result, you may miss this important notification. To help you identify the deactivation message, this email contains the following elements:

* **From:** The deactivation email comes from `aam-noreply@adobe.com`. Pro-tip: Don't reply to this email.

* **Subject line:** Subscription to *name of data feed here* is Cancelled. 

* **Attachments:** The email includes an attachment titled, " `list-of-affected-entities-by-feed-revocation.csv`." That is a convoluted way of saying the attachment lists all the traits included in the cancelled feed. As a data buyer, you should review this attachment. It will help you find and remove deactivated traits from your segments and [algorithmic models](../../../features/algorithmic-models/understanding-models.md).

## Deactivated Trait List {#deactivation-trait-list}

The list that accompanies a deactivation email contains the fields as shown below.

<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data Feed ID</span></b> </p> </td> 
   <td colname="col2"> <p>ID of the deactivated data feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data Feed Name</span></b> </p> </td> 
   <td colname="col2"> <p>Name of the deactivated data feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Trait SID</span></b> </p> </td> 
   <td colname="col2"> <p>Deactivated trait IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Trait Name</span></b> </p> </td> 
   <td colname="col2"> <p>Deactivated trait names. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Segment SID</span></b> </p> </td> 
   <td colname="col2"> <p>ID of the segment that contains deactivated traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Segment Name</span></b> </p> </td> 
   <td colname="col2"> <p>Name of the segment that contains deactivated traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo Model ID</span></b> </p> </td> 
   <td colname="col2"> <p>The ID of the algorithmic model that contain deactivated traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo Model Name</span></b> </p> </td> 
   <td colname="col2"> <p>The names of algorithmic models that contain deactivated traits. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Remove Deactivated Traits {#remove-deactivated-traits}

As a data buyer, you're responsible for removing the traits in a cancelled feed from all your active/in-use or inactive segments. Removal options include:

* Bulk removal with the [REST APIs](../../../api/rest-api-main/rest-api-main.md) or the [Bulk Management Tools](../../../reference/bulk-management-tools/bulk-management-intro.md).

* Manually search for affected segments and remove deactivated traits using [!UICONTROL Segment Builder]. See [Remove Traits from a Segment](../../../features/segments/segment-builder.md#segment-builder-controls-traits).

>[!NOTE]
>
>Removing traits from active algorithmic models or destinations affects scale and targeting accuracy. Try to replace revoked traits with new, active traits if possible.

[Unsubscribe from the deactivated data feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) after you remove all the revoked traits from your account. If this is a temporary deactivation, you can re-subscribe after the data provider finishes making their required changes and reactivates the feed. As with most things, good communication with your partners (the data provider and [!DNL Adobe]) can help you work through this process.

## Understanding the Plan Details Page in Audience Marketplace {#marketplace-buyer-details}

When you click the name of a data plan in the [!UICONTROL Marketplace], [!DNL Audience Manager] provides information that can help you make informed choices about subscribing to a data feed.

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

This page gives you the following information:

1. **Basic Plan Information**. This includes feed information such as:
   * Data feed name. For example, as shown above, the name of this feed is "Sample Data Feed."
   * The name of the data provider;
   * Data Feed ID;
   * Description;
   * Number of traits in the feed;

1. Plan Information Buttons.
   * Click **[!UICONTROL Explore All Traits]** to see details about all the traits in the selected data feed.
   * Click **[!UICONTROL Request More Details]** to ask the data provider questions about the selected data feed or to request a discount. This feature sends your comments and questions directly to the data provider.
  
1. Data Feed Report Metrics. The Venn diagram (and related metrics) shows you trait overlap data for the last 30 days. See [The Marketplace: About](marketplace-data-buyers.md#about-marketplace) for details.
   * **[!UICONTROL 30 Day Overlapped Uniques]**: The number of unique users in your account that overlap with the users in the provider’s account. For a definition of unique users, see AAM UUID in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).
   * **[!UICONTROL 30 Day Provider Unique Users]**: The number of unique users coming from the provider's account.
   * **[!UICONTROL Your Unique Users]**: The number of unique users coming from your account.

1. **[!UICONTROL Plan Details]** Table. This table shows you the use cases that you can subscribe to the data feed for, as well as its pricing model. See [Understanding Data Feed Use Cases](#use-cases).

1. Plan Action Buttons.
   * Click **[!UICONTROL Cancel]** to leave the page without making changes.
   * Click **[!UICONTROL Review & Subscribe]** to subscribe to a data feed. This button is greyed out until you switch a [!UICONTROL Subscription] toggle to [!UICONTROL On]. See also [Subscribe to a Public Data Feed](#subscript-public-data-feed) and [Subscribe to a Private Data Feed](#subscript-private-data-feed).

## Understanding Data Feed Use Cases {#use-cases}

As an [!UICONTROL Audience Marketplace] data buyer, you can purchase data for overlap, modeling, and activation use cases. Each use case is designed for a specific purpose and limits what you can do with the data. These use case descriptions can help you make the right decision about which type of data plan to buy.

## Make Comparisons with Segments and Overlap Plans {#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### Segments and Overlap

This use case lets you compare your traits with provider traits in a [trait-to-trait overlap report.](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) Also, you can create or add provider traits to a segment and make additional comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports. Overlap comparisons can help you:

* **Extend audience reach:** Low overlap suggests your traits contain users you have not seen before. You may want these traits to try and reach new users.
* **Enhance existing audiences:** High overlap suggests your traits are similar to those owned by the data provider. You may want these traits to help make targeted, incremental improvements to an already developed audience.

### Algorithmic Models

This use case lets you evaluate supplier traits against your traits with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). For example, our algorithmic modeling system uses one of your traits as a basis for comparison against a supplier trait. When the model runs, it can show if audiences in supplier traits share similar conversion attributes to your traits.

### Activation

This use case lets you send data to a [destination](../../../features/destinations/destinations.md). In [!DNL Audience Manager], a destination is any third-party system (ad server, [!DNL DSP], [!DNL DMP], exchange, etc.) that you want to share data with. However, with an [!UICONTROL Activation] use case, you cannot run overlap reports or test the data in an algorithmic model.

>[!MORELIKETHIS]
>
>* [Billing and Impression Allocation for CPM Data Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Billing and Impression Allocation for Flat Fee Data Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [How to Report CPM Usage](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
>* [Subscribe to a Public Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
>* [Discounts for Data Buyers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
>* [The Marketplace: About](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)
