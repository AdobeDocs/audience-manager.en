---
description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Data Sampling and Error Rates in Selected Audience Manager Reports
uuid: e75d78f0-4805-4cb0-aec1-1c532c588bc0
index: y
internal: n
snippet: y
translate: y
---

# Data Sampling and Error Rates in Selected Audience Manager Reports

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../c_features/c_analytics/report-sampling.md#section_C0A9E607D6E643E792347A146811ACB4" format="dita" scope="local"> Data Sampling Ratio and Minimum Requirements</a> </li> 
 <li> <a href="../../c_features/c_analytics/report-sampling.md#section_9C05B57627924E08954ACF1928C102E7" format="dita" scope="local"> Error Rates</a> </li> 
 <li> <a href="../../c_features/c_analytics/report-sampling.md#section_F6ECF42C292B4989B9E778B6A9628C05" format="dita" scope="local"> Reports That Use Sampled Data</a> </li> 
</ul>



## Data Sampling Ratio and Minimum Requirements {#section_C0A9E607D6E643E792347A146811ACB4}

Some [!DNL  Audience Manager] reports display results based on a sampled set of the total amount of available data. The sampled data ratio is 1:54. For reports that use sampled data, this means your results are based on 1 record out of every set of 54 records. These reports use sampled data because they need a tremendous amount of computing power to generate results. Sampling helps strike a balance between reduced computational demands, maintaining system performance, and providing accurate results. 

Reports that use sampling exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows: 


* Traits: 28,000 over a 14-day period.
* Segments: 70,000 real-time users over a 14-day period.


## Error Rates {#section_9C05B57627924E08954ACF1928C102E7}

Errors can occur in reports that generate overlap data. An error is defined as the percentage of records that: 


* Should not have been included in a report but were added anyway.
* Should have been included in a report but were left out.


It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Data sets that have a lot of records generate fewer errors than sets with a small number of records. Let's look at this assertion in a more quantitative manner. As shown in the following table, for a set number of records, 95% of your report results will be below a specific error rate. 



<table id="table_CD78C9383C0147818F99FDB5D85B44D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Number of Records </th> 
   <th colname="col2" class="entry"> Error Rate </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>500 - 1,000 </p> </td> 
   <td colname="col2"> <p>95% are under a 42% error rate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1,000 - 1,500 </p> </td> 
   <td colname="col2"> <p>95% are under a 34% error rate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10,000 - 50,000 </p> </td> 
   <td colname="col2"> <p>95% are under a 14% error rate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50,000 </p> </td> 
   <td colname="col2"> <p>95% are under a 6% error rate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>100,000 </p> </td> 
   <td colname="col2"> <p>95% are under a 4% error rate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>500,000 (or more) </p> </td> 
   <td colname="col2"> <p>95% are under a 2% error rate. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Reports That Use Sampled Data {#section_F6ECF42C292B4989B9E778B6A9628C05}

The [!DNL  Audience Manager] reports that use sampled data include: 


* [ Overlap reports](../../c_features/c_analytics/c_dynamic_reports/c_dynamic_reports.md#concept_88ADC775F1E9458582A3285B29B76A46) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [ Addressable Audience](../../c_features/addressable-audiences/addressable-audiences.md#concept_8E0BAEF0978F4968B21482E79E601889) data (customer- and segment-level data).
* The [ Total Devices](../../c_features/profile-link-intro/profile-link-metrics.md#section_23F45E4C374241709A246058F4D92A23) metric for a [!UICONTROL  Profile Merge Rule].

