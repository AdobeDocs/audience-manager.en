---
description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: GDPR Considerations for Destinations
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
---

# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).

Adobe partners own their business processes and may decide to update their integration requirements with Audience Manager from time to time. We are proactively working with our Audience Manager partner ecosystem to keep our customers apprised of changes.

On this page:

<ul class="simplelist"> 
 <li><a href="../../overview/aam-gdpr/aam-gdpr-partners.md#section_F462002CBE7A4B17B20B758C3F2A05C7"> Audience Manager Partner Updates - ID Syncs</a> </li> 
 <li><a href="../../overview/aam-gdpr/aam-gdpr-partners.md#section_583C4069B3774EF29A77B2A466DDF944"> Audience Manager UI Update - Yahoo/Oath/DataX Integration</a> </li> 
 <li><a href="../../overview/aam-gdpr/aam-gdpr-partners.md#section_49E63A6345D648F4AED87CD33B36F5FB"> Audience Manager Partners With Unsegmentation Capabilities</a> </li> 
</ul>

## Audience Manager Partner Updates - ID Syncs {#section_F462002CBE7A4B17B20B758C3F2A05C7}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#section_583C4069B3774EF29A77B2A466DDF944}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. Their parameters inform Yahoo/Oath/DataX that they have the rights to process a certain segment as a Data Processor or as a Data Controller. As a result, Audience Manager customers sending segments to a Yahoo/Oath/DataX destination must designate the appropriate parameter (Processor or Controller), based on their agreement with Oath.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#section_49E63A6345D648F4AED87CD33B36F5FB}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or 
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](assets/AAM-Partners-Jan2019.xlsx) to see which Audience Manager activation partners support unsegment. 
