---
description: Answers to common privacy- and data-related questions or issues.
seo-description: Answers to common privacy- and data-related questions or issues.
seo-title: Privacy and Data Retention FAQ
solution: Audience Manager
title: Privacy and Data Retention FAQ
uuid: cf20feb2-3ffb-4887-83c5-c8c9e79b9b3e
index: y
internal: n
snippet: y
translate: y
---

# Privacy and Data Retention FAQ

Answers to common privacy- and data-related questions or issues.



Contents: 



<ul class="simplelist"> 
 <li> <a href="../faq/faq-privacy.md#section_F3C1DAF4F16F43B9AE817B8828C3DD74" format="dita" scope="local"> Privacy FAQ </a> </li> 
 <li> <a href="../faq/faq-privacy.md#section_20FF2BAAAA504153B36C420A5ECFB458" format="dita" scope="local"> Data Retention FAQ </a> </li> 
</ul>



## Privacy FAQ {#section_F3C1DAF4F16F43B9AE817B8828C3DD74}




>[!TIP]
>
>Visit the [Adobe Privacy Center](http://www.adobe.com/privacy.html) for more information. 



**How does Audience Manager use cookies and what cookies does it set?** 


See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html). 


**Can Audience Manager clients in the US target users on EU properties?** 


Yes. Audience Manager works with clients who have international properties and inventory. The EU has strict privacy laws, but Audience Manager has clients who use first-party data for audience targeting in Europe. Audience Manager can support targeting to EU audiences, but it is your responsibility to comply with local privacy regulations. 

<!-- <p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p> -->

## Data Retention FAQ {#section_20FF2BAAAA504153B36C420A5ECFB458}



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
   <td colname="col2"> <p>90-days (removed after 90-days of no activity). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>Reporting</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>Actionable Log Files</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>Data is kept indefinitely, but customers can set an expiration period by setting a time-to-live interval on their traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8" format="dita" scope="local"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer Data Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. The retention period is 8 days. For more details about CDF, please refer to <a href="../c_features/cdf-files.md#concept_114B993EC5E246AE8CDD55E695B344FC" format="dita" scope="local"> CDF Intro</a> and <a href="../faq/faq-cdf.md#concept_E832A7307FA0475C918F95116C21CBC6" format="dita" scope="local"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappings between synchronized IDs </p> </td> 
   <td colname="col2"> <p>Data is kept indefinitely. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inbound data </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md#concept_CA81A40C5DD643F899490355C737CE9C" format="dita" scope="local"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Outbound data </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. The retention period is 8 days. For more details about Outbound data, please refer to <a href="../c_integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-transfers.md#concept_11A07DEA9D49404A94C62931B8499E43" format="dita" scope="local"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Trait Qualification Data Retention {#section_73A6DFBF24EA464C9544DA9B02ED6845}



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
   <td colname="col2"> <p>We impose a limit of 100,000 trait qualifications for each user profile. The limit applies to authenticated profiles and device profiles. If a user profile reaches this limit, we will delete the oldest trait qualifications, on a first-in, first-out basis. </p> <p>For more details, read our <a href="../c_features/traits/trait-qualification-reference.md#section_CA54FECC85114000A1907C1D4535AB2D" format="dita" scope="local"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

