---
description: Common elements responsible for low Addressable Audience match rates or discrepancies in reported numbers.
seo-description: Common elements responsible for low Addressable Audience match rates or discrepancies in reported numbers.
seo-title: Causes of Low Match Rates for Addressable Audiences
solution: Audience Manager
title: Causes of Low Match Rates for Addressable Audiences
topic: DIL API
uuid: 72b2ed2f-8a9d-4d14-8b02-4431e1174c5b
index: y
internal: n
snippet: y
translate: y
---

# Causes of Low Match Rates for Addressable Audiences



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
   <td colname="col2"> <p>Most server-to-server integrations rely on synchronization processes facilitated by third-party cookies. However, mobile environments do not use third-party cookies. As a result, your Addressable Audience numbers may seem low compared to segment size. </p> <p>As of January 2018, you can activate mobile audiences in the same Google and Adobe Advertising Cloud destinations set up for cookie-based audiences. While this means that you can send segments with combined cookie and mobile ID membership to your Google and Advertising Cloud destinations, keep in mind that Addressable Audiences only display the overlap between cookie IDs and destinations. Audience Manager sends 100% of mobile audiences to destinations, but mobile audiences are not measured by the Addressable Audience metric. </p> <p> <p>Note:  For example, take a segment with a population of 1,000,000. If you map this segment to a Google or Adobe Advertising Cloud destination, you might see an Addressable Audience of 700,000 devices and a Match Rate of 70%. The membership of 700,000 consists of cookie IDs which have an ID sync with the destination. Your Addressable Audience might, in fact, be much higher, because addressable mobile IDs do not appear in this metric. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari Traffic</b> </p> </td> 
   <td colname="col2"> <p>Safari blocks third-party cookies. This prevents Audience Manager from synchronizing with the destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tracked Media Impressions</b> </p> </td> 
   <td colname="col2"> <p>Due to ad server best practices, ID syncs are not made within ad tags. Customers who do a large amount of offsite advertising will not synchronize users to third-party integrations in those environments. Also, a large amount of collected media impression data could reduce addressable audience numbers. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ Troubleshooting with Addressable Audiences ](addressable-audiences-troubleshooting.md#concept_22DACEC796894D04B94D6BF047F94EB4)
