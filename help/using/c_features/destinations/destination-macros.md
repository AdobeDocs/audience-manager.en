---
description: Describes the macros you can add to a destination URL.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: Destination Macros Defined
uuid: 2bcde7a2-2696-4693-b977-ca7e103265ec
index: y
internal: n
snippet: y
translate: y
---

# Destination Macros Defined

Describes the macros you can add to a destination URL.

## Destination Macros Defined {#reference_B2F4AE643702440D879EFFE4A3FAAEDB}

Describes the macros you can add to a destination URL.

<!-- destination-macros.xml -->

When creating a URL destination, you can insert the following macros into the URL string. Check with your data/destination partner about proper macro placement within the destination URL.

>[!NOTE]
>
>Macros are optional unless indicated otherwise. *Italics* indicates a variable placeholder.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Explanation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> %alias%</span> </p> </td> 
   <td colname="col2"> <p>Required. </p> <p>Defines the location of the mapped segment value in a destination URL. Usually this is the <span class="varname"> Segment ID</span>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> %did%</span> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">%dpid_<span class="varname"> data source id</span>%</span> </p> </td> 
   <td colname="col2"> <p>The <span class="varname"> data source id</span> corresponds to the identifier for a data source passed in to the macro. </p> <p>Let's look at how this works in a simple example. In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <span class="codeph"> 1</span> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <span class="codeph"> CustomerABC</span> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <span class="codeph"> 1:CustomerABC</span>. </li> 
    </ul> <p>To do this with the <span class="codeph">%dpid_<span class="varname"> data source id</span>%</span>, the <span class="keyword"> Audience Manager</span> partner would format the macro like this: </p> 
    <ul class="simplelist"> 
     <li> <span class="codeph"> %dpid_1%</span> </li> 
    </ul> <p>The macro will replace <span class="codeph"> 1</span> with <span class="codeph"> CustomerABC</span>. </p> <p> 
     <draft-comment>
       Based on AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> %http_proto%</span> </p> </td> 
   <td colname="col2"> <p>Detects the protocol used in the parent webpage and inserts it into the destination URL. For example: 
     <lines></lines> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> %mcid%</span> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="keyword"> Experience Cloud</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> %region%</span> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. This is achieved through DNS, which is able to detect the visitor's location and direct them to the appropriate datacenter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> %rnd%</span> </p> </td> 
   <td colname="col2"> <p>Performs a cache busting function by inserting a random number into the destination URL. This prevents browsers from serving cached content. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> %timestamp%</span> </p> </td> 
   <td colname="col2"> <p>Inserts a UNIX timestamp into the destination URL to prevent browsers from serving cached content. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#concept_247813563F26479296AF44B250968BBB}

The `%rnd%` and `%timestamp%` macros insert unique values into a URL string to prevent browser caching.

## Cache Busting with %rnd% and %timestamp% {#section_4A1CBFBCB1F74E55BB3A8345E5174332}

<!-- c_dest_cache_busting.xml -->

Browsers cache (save) save frequently requested content in memory. When a page loads, saved content serves from the cache rather than from a remote server. This process helps maintain efficient download times because data serves locally rather than from another location. However, because caching does not require a server call, it can skew reporting by artificially lowering the number of unique requests.

Cache busting prevents browsers from saving and reusing content. This technique uses code that inserts a random number or time stamp into a URL string, which makes it look unique to the browser. As a result, each HTTP call is counted as a separate request to the server. Forcing a new server call for each request helps maintain reporting accuracy and reduce discrepancies. [!DNL Audience Manager] provides two macros for cache busting:

* `%rnd%`: Inserts a random number into a URL. 
* `%timestamp%`: Inserts the Unix date/time into a URL.

## Comparing %rnd% and %timestamp% {#section_DA7D8DD8FCB74C259C621121C50BF0FB}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they'll get the same date/time value. As a result, the URL is not unique and multiple calls are counted only once. However, `%rnd%` generates a unique numeric value for each call (even when users see the same page simultaneously). This means the URL string contains different values and is counted as unique. 

>[!MORE_LIKE_THIS]
>
>* [Destination Macros Defined](destination-macros.md#reference_B2F4AE643702440D879EFFE4A3FAAEDB)
