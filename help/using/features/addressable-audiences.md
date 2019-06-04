---
description: An overview of the Addressable Audience feature and use cases.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Addressable Audiences
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
---

# Addressable Audience {#addressable-audiences}

An overview of the Addressable Audience feature and use cases.

## What is an Addressable Audience? {#addressable-audience-description}

The [!UICONTROL Addressable Audiences] feature shows you the overlap between the audiences you see across all of your properties where [!DNL Audience Manager] collects data and your selected destination. To help you understand this concept, take a look at the illustration below. The overlap between each circle represents the different types of addressable audiences.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audience Manager's Addressable Audience for a Destination</b> </p> </td> 
   <td colname="col2"> <p>A count of all devices that have interacted with all Audience Manager customers at the platform-level during the report look-back period and that could be matched with your chosen destination. </p> <p>This metric is useful because it shows you: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Customer Total Audience</b> </p> </td> 
   <td colname="col2"> <p>A count of devices that have realized either a rule-based trait on your properties or an onboarded trait from your offline files during the look-back window. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Customer Addressable Audience</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>A count of overlap of devices that have realized either a rule-based trait or an onboarded trait during the look-back window and devices that we have an ID sync with the chosen destination regardless of the time of syncs. </p> 
    </draft-comment> <p>This metric represents devices that: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Have an ID sync with the chosen destination regardless of the time of syncs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Customer Match Rate</b> </p> </td> 
   <td colname="col2"> <p>Customer Addressable Audience ÷ Customer Total Audience expressed as a %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Total Segment Population</b> </p> </td> 
   <td colname="col2"> <p>A count of all the devices that were a member of your segment during the report look-back period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>The number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Tip: When used with the 1-day look-back period, this metric can help you understand the current state of your segments. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Match Rate</b> </p> </td> 
   <td colname="col2"> <p>Segment Addressable Audience ÷ Total Segment Population expressed as a %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

The [!UICONTROL Addressable Audience] feature turns this abstract concept into quantifiable data. In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences] is located in **[!UICONTROL Audience Data > Destinations]**. Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

 Click on the name of a server-to-server destination to view your addressable audience data. Note, this feature returns data for server-to-server destinations only and access requires administrator permissions.

![](assets/addressableAudiences.png)

Reviewing this data can help you with:

* **Forecasting and planning:** [!UICONTROL Segment Addressable Audience] data gives you more granularity into the segments you are planning to send to a destination for audience targeting and activation.

* **Performance reviews:** The [!UICONTROL Addressable Audiences] feature is also a troubleshooting tool. It lets you review campaign performance, understand campaign reach, and lets you cross-check with targeting/activation partners if you don't see the results you expect.

### Prospecting with Third-Party Data and Implications for Match Rates

Before purchasing third-party data for audience acquisition, customers can validate the overlap with other data providers. This can help you make an informed decision prior to buying new data. The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. Your [!DNL Adobe] consultant can help you identify additional relevant data sources to optimize prospecting campaigns.

### Mobile Users and Match Rates

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. The date range options include:

* [!UICONTROL Last 1 Day] (This interval runs from Midnight to Midnight of the previous 24-hour period. It is not a real or current-time metric.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

The [!UICONTROL Addressable Audience] and [!UICONTROL Destination] metrics return a count of unique users for the selected time interval. For example, a visitor is only counted once, even if they come to your site multiple times. The first visit is the unique visit and gets recorded. The subsequent visits are returning visits and are not counted because they're not unique.

Date ranges contain data for the selected time interval or older. And, the data ages out of each report interval as time passes. For example, let's assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. In the reports, these visitors:

* *Will be* included in the results returned by the longer time intervals (60 days, 90 days, and Lifetime).
* *Will not be* included in the shorter intervals that precede the [!UICONTROL Last 30 Day] option (Current, 7 days, and 14 days).

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. They have aged out of the 30 day interval. Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. These metric provide a comprehensive view of audience size for your account.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Customer Addressable Audience</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>A count of overlap of devices that have realized either a rule-based trait or an onboarded trait during the look-back window and devices that we have an ID sync with the chosen destination regardless of the time of syncs. </p> 
    </draft-comment> <p>This metric represents devices that: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Have an ID sync with the chosen destination regardless of the time of syncs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Customer Total Audience</b> </p> </td> 
   <td colname="col2"> <p>A count of devices that have realized either a rule-based trait on your properties or an onboarded trait from your offline files during the look-back window. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Customer Match Rate</b> </p> </td> 
   <td colname="col2"> <p>Customer Addressable Audience ÷ Customer Total Audience expressed as a %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

These metrics return data on segment membership. They help provide a more granular and accurate view of the audience size for each of your segments.

>[!NOTE]
>
>The way the look-back window is applied at the segment level is different from that at the customer level. Visitors can come to the site and realize a trait 10 days ago, and they could qualify for a segment since then and dropped out of the segment 2 days ago. When the 7 day look-back is applied, these visitors will be counted at the segment level but not at the customer level.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>The number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Tip: When used with the 1-day look-back period, this metric can help you understand the current state of your segments. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total Segment Population</b> </p> </td> 
   <td colname="col2"> <p>A count of all the devices that were a member of your segment during the report look-back period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Match Rate</b> </p> </td> 
   <td colname="col2"> <p>Segment Addressable Audience ÷ Total Segment Population expressed as a %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

This metric returns data on activities collected across all Audience Manager customers. They can provide a broader view of the customer's audience compared with the aggregated Audience Manager customers.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager's Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>A count of all devices that have interacted with all Audience Manager customers at the platform-level during the report look-back period and that could be matched with your chosen destination. </p> <p>This metric is useful because it shows you: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn't compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. These are separate, different, and independent metrics. As described in the definitions above, each of these is derived from different data sets. Given this, you should avoid deriving any conclusions if one metric is larger than the other. All you can say when comparing these is that:

* [!UICONTROL Customer Addressable Audiences] is based on trait realizations *for your own, first-party data*. This metric provides a broad, comprehensive view of your integration with a data partner.

* [!UICONTROL Segment Addressable Audiences] is based on segment qualifications *for your own first-party data, plus second and third-party data*. This metric provides a granular, more accurate view of your addressable audiences in a targeting platform.

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cause </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Mobile Traffic</b> </p> </td> 
   <td colname="col2"> <p>Most server-to-server integrations rely on synchronization processes facilitated by third-party cookies. However, mobile environments do not use third-party cookies. As a result, your Addressable Audience numbers may seem low compared to segment size. </p> <p>As of January 2018, you can activate mobile audiences in the same Google and Adobe Advertising Cloud destinations set up for cookie-based audiences. While this means that you can send segments with combined cookie and mobile ID membership to your Google and Advertising Cloud destinations, keep in mind that Addressable Audiences only display the overlap between cookie IDs and destinations. Audience Manager sends 100% of mobile audiences to destinations, but mobile audiences are not measured by the Addressable Audience metric. </p> <p> <p><b>Note</b>:  For example, take a segment with a population of 1,000,000. If you map this segment to a Google or Adobe Advertising Cloud destination, you might see an Addressable Audience of 700,000 devices and a Match Rate of 70%. The membership of 700,000 consists of cookie IDs which have an ID sync with the destination. Your Addressable Audience might, in fact, be much higher, because addressable mobile IDs do not appear in this metric. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari Traffic</b> </p> </td> 
   <td colname="col2"> <p>Safari blocks third-party cookies. This prevents Audience Manager from synchronizing IDs with the destination. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, you can expect your addressable audiences not to include Safari users. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tracked Media Impressions</b> </p> </td> 
   <td colname="col2"> <p>Due to ad server best practices, ID syncs are not made within ad tags. Customers who do a large amount of offsite advertising will not synchronize users to third-party integrations in those environments. Also, a large amount of collected media impression data could reduce addressable audience numbers. </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

For example, let's say you send a segment to a destination and that destination shows low reporting numbers. Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. A low match rate shows your destination isn't all that great for your selected segments. However, a difference in the total addressable audience numbers between Audience Manager and the destination indicates an integration, synchronization, or other technical problem. In these cases, contact your account manager.