---
description: Lists and defines the data elements and arrays in a Customer Data Feed (CDF) file, by order of appearance. Definitions include data types, but this information is not part of a CDF file.
seo-description: Lists and defines the data elements and arrays in a Customer Data Feed (CDF) file, by order of appearance. Definitions include data types, but this information is not part of a CDF file.
seo-title: Customer Data Feed Contents Defined
solution: Audience Manager
title: Customer Data Feed Contents Defined
uuid: 954e3ad1-ad82-484d-989d-18a1241302de
index: y
internal: n
snippet: y
translate: y
---

# Customer Data Feed Contents Defined



## Definitions {#section_DB2A76D38BCD4FE3832B84FD835F153C}

A CDF file includes some or all of the fields defined below. For information about internal file organization, see [ Customer Data Feed File Structure](../../c_features/cdf-intro/cdf-file-structure.md#concept_4F215D39A64A43CCAE8791FCD3D5232D). 



<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Data Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Event Time </p> </td> 
   <td colname="col2"> <p>Timestamp </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">The time of the page event or the event call itself, although it may be close to those times. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Related to the DCS hour in the file name. See also, <a href="../../c_features/cdf-intro/cdf-time-differences.md#concept_C907608AC1ED44BA8EF870F45E5A9CB9" format="dita" scope="local"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Device </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. See also, <a href="../../c_reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8" format="dita" scope="local"> Index of IDs in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Container ID </p> </td> 
   <td colname="col2"> <p>Numeric </p> </td> 
   <td colname="col3"> <p>The ID of the container that fires ID syncs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realized Traits </p> </td> 
   <td colname="col2"> <p>Numeric Array </p> </td> 
   <td colname="col3"> <p>An array of trait IDs that contains all the traits a visitor realized (qualified for) in the event call. </p> <p>Note that the array can contain traits for which the visitor had qualified before and for which they re-qualify through this event call. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realized Segments </p> </td> 
   <td colname="col2"> <p>Numeric Array </p> </td> 
   <td colname="col3"> <p>An array of segment IDs that contains all the segments a visitor realized (qualified for) in the event call. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Request Parameters </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>A string that captures all the parameters (variables, IDs, key-value pairs, etc.) passed in on the event call. </p> <p>Shortened example: </p> <p> <span class="codeph"> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referer Data Type </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>The unencoded URL of the referring page (if any). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP Data Type </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>The IP address for the visitor captured in the event call. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MCDevice </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>The Experience Cloud ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>All Segments </p> </td> 
   <td colname="col2"> <p>Numeric Array </p> </td> 
   <td colname="col3"> <p>An array of segment IDs that contains previously realized segments and new segments the visitor is qualified for. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>All Traits </p> </td> 
   <td colname="col2"> <p>Numeric Array </p> </td> 
   <td colname="col3"> <p>An array of first and third-party trait IDs that contains previously realized traits and new traits the visitor has qualified for since the last generated data feed. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ Customer Data Feed File Structure ](cdf-file-structure.md#concept_4F215D39A64A43CCAE8791FCD3D5232D)
>* [ Customer Data Feed FAQ ](cdf-faq.md#concept_E832A7307FA0475C918F95116C21CBC6)
