---
description: Lists and defines the elements in your Customer Data File (CDF) file name.
seo-description: Lists and defines the elements in your Customer Data File (CDF) file name.
seo-title: Customer Data Feed File Naming Conventions
solution: Audience Manager
title: Customer Data Feed File Naming Conventions
uuid: 3ec34174-8b3c-42af-9ba8-7f34537b721e
index: y
internal: n
snippet: y
translate: y
---

# Customer Data Feed File Naming Conventions



## CDF File Name: Syntax and Example {#section_C06A94AD48E84B758645FB74BAEFAB34}

A typical CDF file name contains the elements listed below. Note, *italics* indicates a variable placeholder: 


<ul class="simplelist"> 
 <li> <b>Syntax:</b> <span class="codeph"> s3://aam-cdf/<span class="varname"> your s3 bucket name</span>/day=<span class="varname"> yyyy-mm-dd</span>/hour=<span class="varname"> hh</span>/<span class="varname"> AAM_CDF_partner ID_AAM process ID</span>_0.gz</span> </li> 
 <li> <b>Example:</b> <span class="codeph"> s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz</span> </li> 
</ul>



In your S3 storage bucket, files are sorted in ascending order by Partner ID (PID), day, and hour. 

## CDF File Name Elements Defined {#section_D8D955D05105486EB77C4F5DA08C7CBD}

The following table lists and defines the elements in a CDF file name. 



<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Name Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> s3://aam-cdf/</span> </p> </td> 
   <td colname="col2"> <p>This is the default, root storage bucket for your CDF file on an Amazon S3 server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> your S3 bucket name</span> </span> </p> </td> 
   <td colname="col2"> <p>The name of the read-only, S3 bucket that holds your CDF files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">day=<span class="varname"> yyyy-mm-dd</span></span> </p> </td> 
   <td colname="col2"> <p>The date your file was processed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">hour=<span class="varname"> hh</span></span> </p> </td> 
   <td colname="col2"> <p>A time value expressed in 24-hour notation and set in the UTC time zone. See also, <a href="../../c_features/cdf-intro/cdf-time-differences.md#concept_C907608AC1ED44BA8EF870F45E5A9CB9" format="dita" scope="local"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> partner ID</span> </span> </p> </td> 
   <td colname="col2"> <p>Your partner ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> AAM process ID</span>_0</span> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> .gz</span> </p> </td> 
   <td colname="col2"> <p>A gzip file extension. CDF files are gzip compressed. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ Customer Data Feed File Name Times and File Content Times... ](cdf-time-differences.md#concept_C907608AC1ED44BA8EF870F45E5A9CB9)
>* [ Customer Data Feed FAQ ](cdf-faq.md#concept_E832A7307FA0475C918F95116C21CBC6)
