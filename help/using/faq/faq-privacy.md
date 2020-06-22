---
description: Answers to common privacy- and data-related questions or issues.
seo-description: Answers to common privacy- and data-related questions or issues.
seo-title: Privacy and Data Retention FAQ
solution: Audience Manager
title: Privacy and Data Retention FAQ
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
---

# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Answers to common privacy- and data-related questions or issues.

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**How does Audience Manager use cookies and what cookies does it set?**

See [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**Can Audience Manager clients in the US target users on EU properties?**

Yes. Audience Manager works with clients who have international properties and inventory. The EU has strict privacy laws, but Audience Manager has clients who use first-party data for audience targeting in Europe. Audience Manager can support targeting to EU audiences, but it is your responsibility to comply with local privacy regulations.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Data Retention FAQ {#data-retention-faq}

The following table lists the retention times for different data types and storage systems.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Type, Source, or Storage </th> 
   <th colname="col2" class="entry"> Data Retention Period </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Back-end servers </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> Audience Manager deletes user data from our back-end servers 120 days after last seeing a user on the Audience Manager platform. If <span class="keyword"> Audience Manager</span> records user activity within this 120-day cycle, we will keep this data for another 120-days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge servers </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>Audience Manager deletes user data from our edge servers 14 days after last seeing a user on the Audience Manager platform. If <span class="keyword"> Audience Manager</span> records user activity in within this 14-day cycle, we will keep this data for another 14-days. If the user becomes active again after the 14-day period, there will be a delay between that first new page view and when the user becomes actionable. It takes 6-18 hours to get the full profile back out to the edge center after more than 14-days of inactivity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw logs </p> </td> 
   <td colname="col2"> <p>180-days (removed after 180-days of no activity). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>Reporting</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>Actionable Log Files</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. However, you can use the Audience Manager user interface to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. You can accomplish this when creating or editing a Cross-Device data source.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer Data Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. The retention period is 8 days. For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappings between synchronized IDs </p> </td> 
   <td colname="col2"> <p>The lifespan of the <a href="../features/administration/usage-limits.md#id-mapping-limits"> ID mappings</a> between Audience Manager cookie IDs (<a href="../reference/ids-in-aam.md">Audience Manager Unique User IDs or AAM UUIDs</a>) and 3rd party cookie IDs is limited to 120 days. The lifespan of the ID mapping resets each time the Audience Manager cookie is seen across the Audience Manager network. The most recent ID mapping sync will be preserved for the life of the associated <a href="../reference/ids-in-aam.md">Audience Manager Unique User ID (AAM UUID)</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inbound data </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Outbound data </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. The retention period is 8 days. For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

The table below lists the retention options for trait qualifications.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait Operation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Delete a trait </p> </td> 
   <td colname="col2"> <p>Deleting a trait removes the trait qualification data from all the user profiles that had qualified for the trait in the past. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trait limit reached </p> </td> 
   <td colname="col2"> <p>We impose a limit of 100,000 trait qualifications for each user profile. The limit applies to authenticated profiles and device profiles. If a user profile reaches this limit, we will delete the oldest trait qualifications, on a first-in, first-out basis. </p> <p>For more details, read our <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

