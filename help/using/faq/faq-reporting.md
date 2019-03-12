---
description: Common reporting-related questions and issues.
seo-description: Common reporting-related questions and issues.
seo-title: Reporting FAQ
solution: Audience Manager
title: Reporting FAQ
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
---

# Reporting FAQ{#reporting-faq}

Common reporting-related questions and issues.

<br>&nbsp;

<!-- 

faq_reports.xml

 -->

**For new onboarded traits, why does the [!UICONTROL Trait Graph] sometimes display lower than expected numbers or 0?**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn't show any results or shows lower than expected numbers. This happens when the volume of data we receive is so great that the inbound processing job cannot finish ingesting this information until after the reporting deadline for that day. 

As a result, this data is sent to the reporting system late and won't show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br>&nbsp;

**Some segments are missing from an [!UICONTROL Overlap] report. Where are they?**

To help reduce computational demand, these reports omit statistically insignificant data from the results. Your segments are not missing, they're just dropped because they do not yield meaningful results or useful pools of users that you can target. See also:

* [Reports and Data Sampling Methodologies](../reporting/report-sampling.md#concept_624BB1069F8A4CBD948ABD87105329E4) 
* [Counting Unique Users in Overlap and General Reports](../reporting/unique-user-counts.md#concept_4D029582FBEA45B39352A05AF7E3CA37).

<br>&nbsp;

**If I run an email marketing campaign, how can I determine if redirected users come to my site from that campaign or from other sources?**

Append a campaign-specific query string to the URL of the site section you want to monitor. Next, set up a trait rule to capture this variable. For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br>&nbsp;

**What is the difference between real-time and total segment population counts?**

* **Real time:** The number of unique users who are part of the segment and active on your properties during a set time period (i.e., [!DNL Audience Manager] must have recorded activity for that user for the specific period of time). 

* **Total segment population:** An aggregation of all users who are currently classified in that segment.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

 <br>&nbsp;

**I have a segment consisting of just one trait. When I look at Reporting metrics, their counts don't match. Why is that?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md#concept_05EE3010E67F446E8818351292EF7372).

<br>&nbsp;

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**I Inbound a file and my Inbound receipt shows a high number of successfully processed records, but reporting shows much lower numbers. Why?**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br>&nbsp;

**Why are the trait uniques for my cross-device onboarded traits much higher than the total number of onboarded records?**

If you onboard a file for a cross-device data provider keyed off the customer ID, Audience Manager performs a lookup to get all device IDs that are associated with each of the onboarded customer IDs. Audience Manager then assigns the onboarded traits to the device ID associated with the customer ID.

As an example, suppose you have onboarded 100 records. For each of these customer IDs, on average, AAM has associated three device IDs. As a result, the trait that was onboarded is assigned to 300 device IDs.

There are two reasons why a single cross-device customer ID can be associated with multiple device IDs:

* Users are logging in to the same cross-device account from multiple computers/browsers.
* Users are clearing their cookies. Note: “Abandoned” cookies are deleted after 120 days of user inactivity.

<br>&nbsp;

**Why are [!UICONTROL Total Trait Realizations] for my onboared traits always 0?**

[!UICONTROL Total Trait Realizations] correspond to page loads. [!UICONTROL Total Trait Realizations] provide the number of times that specific trait has fired in real-time. This number is calculated for rule-based traits only. Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br>&nbsp;

**I created a trait and the [!UICONTROL Trait Graph] shows a larger number of [!UICONTROL Unique Trait Realizations] than the [!UICONTROL Total Trait Population]. Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. The [!UICONTROL Total Trait Population] should be larger than the [!UICONTROL Unique Trait Realizations] within a couple of days.
