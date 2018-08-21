---
description: Lists and defines metrics provided by Addressable Audiences.
seo-description: Lists and defines metrics provided by Addressable Audiences.
seo-title: Addressable Audience Metrics
solution: Audience Manager
title: Addressable Audience Metrics
topic: DIL API
uuid: f1923cf0-5eef-4fb6-8191-52e4fa7a265a
index: y
internal: n
snippet: y
translate: y
---

# Addressable Audience Metrics


>Contents: 

>
<ul class="simplelist"> 
 <li> <a href="../../c_features/addressable-audiences/addressable-audience-metrics.md#section_0816B56BF5A14CEF8578674DB33D08F3" format="dita" scope="local"> Customer-Level Metrics </a> </li> 
 <li> <a href="../../c_features/addressable-audiences/addressable-audience-metrics.md#section_DDA700BBD12141D384E104E673E551D9" format="dita" scope="local"> Segment-Level Match Metrics </a> </li> 
 <li> <a href="../../c_features/addressable-audiences/addressable-audience-metrics.md#section_DC2CD74AE4D645A7BCD8F90398D1A376" format="dita" scope="local"> Platform-Level Metrics </a> </li> 
 <li> <a href="../../c_features/addressable-audiences/addressable-audience-metrics.md#section_A7178ED5709646C1BBC0A19114E8B1E7" format="dita" scope="local"> Avoid Customer and Segment Addressable Audience Comparisons </a> </li> 
</ul>



## Customer-Level Metrics {#section_0816B56BF5A14CEF8578674DB33D08F3}

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL  Audience Manager]. These metric provide a comprehensive view of audience size for your account. 



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
   <td colname="col2"> <p>A count of overlap of devices that have realized either a rule-based trait or an onboarded trait during the look-back window and devices that we have an ID sync with the chosen destination regardless of the time of syncs. </p> </td> 
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


## Segment-Level Match Metrics {#section_DDA700BBD12141D384E104E673E551D9}

These metrics return data on segment membership. They help provide a more granular and accurate view of the audience size for each of your segments. 


>[!NOTE]
>
>The way the look-back window is applied at the segment level is different from that at the customer level. Visitors can come to the site and realize a trait 10 days ago, and they could qualify for a segment since then and dropped out of the segment 2 days ago. When the 7-day look-back is applied, these visitors will be counted at the segment level but not at the customer level.





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
   <td colname="col2"> <p>The number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. </p> <p> <p type="tip">Note: When used with the 1-day look-back period, this metric can help you understand the current state of your segments. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
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


## Platform-Level Metrics {#section_DC2CD74AE4D645A7BCD8F90398D1A376}

This metric return data on activities collected across all Audience Manager customers. They can provide a broader view of the customer's audience compared with the aggregated Audience Manager customers. 



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
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Avoid Customer and Segment Addressable Audience Comparisons {#section_A7178ED5709646C1BBC0A19114E8B1E7}

You shouldn't compare the [!UICONTROL  Customer Addressable Audience] and [!UICONTROL  Segment Addressable Audience] metrics to determine if one is more significant than the other. These are separate, different, and independent metrics. As described in the definitions above, each of these is derived from different data sets. Given this, you should avoid deriving any conclusions if one metric is larger than the other. All you can say when comparing these is that: 


* [!UICONTROL  Customer Addressable Audiences] is based on trait realizations for your own, first-party data. This metric provides a broad, comprehensive view of your integration with a data partner.
* [!UICONTROL  Segment Addressable Audiences] is based on segment qualifications for your own first-party data and third-party data. This metric provides a granular, more accurate view of your addressable audiences in a targeting platform.

