---
description: URLs for requests, staging and production environments, and versions.
seo-description: URLs for requests, staging and production environments, and versions.
seo-title: API URLs
solution: Audience Manager
title: API URLs
uuid: 654acdad-9ed9-46c5-88e2-923da0b52394
index: y
internal: n
snippet: y
translate: y
---

# API URLs


>This section contains the following information: 
>
>* [ Request URLS ](../../../c_api/c_rest_api_main/c_rest_api_overview/r_rest_urls.md#section_2DBA5BD10E8B4E0DBD51BD36055C5013)
>* [ Environments ](../../../c_api/c_rest_api_main/c_rest_api_overview/r_rest_urls.md#section_5B33F1445F9C49C896C4E9240B5F0CCD)
>* [ Versions ](../../../c_api/c_rest_api_main/c_rest_api_overview/r_rest_urls.md#section_473AE7014EE949E7AD868AB357452673)

## Request URLS {#section_2DBA5BD10E8B4E0DBD51BD36055C5013}

The following table lists the request URLs used to pass in API requests, by method.
<table id="table_C174E7230F6F4D55AC6515FBDBDD265B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Methods </th> 
   <th colname="col2" class="entry"> Request URL </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <b>Algorithmic Modeling</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/models/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/datasources/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Derived Signals</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/signals/derived/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Destinations</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/destinations/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Domains</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/partner-sites/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Folders</b> </td> 
   <td colname="col2"> 
    <ul id="ul_DF2B28E0D85340398D6E00B0BBC2B9B4"> 
     <li id="li_271CAE6807EB4428A77C26F60EFE813D">Traits: <span class="codeph"> https://api.demdex.com/v1/folders/traits </span>/ </li> 
     <li id="li_B3CE481EAA7B4E1E9DD7857A9E5BF297">Segments: <span class="codeph"> https://api.demdex.com/v1/folders/segments </span>/ </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Schema</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/schemas/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Segments</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/segments/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Traits</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/traits/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Trait Types</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/customer-trait-types </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b> Taxonomy</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/taxonomies/0/ </span> </td> 
  </tr> 
 </tbody> 
</table>


## Environments {#section_5B33F1445F9C49C896C4E9240B5F0CCD}

The [!DNL  Audience Manager] APIs provide access to different working environments. These environments help you test code against separate databases without affecting live, production data. The following table lists the available API environments and corresponding resource hostnames. 

|  Environment  | Hostname  |
|---|---|
|  **Production** | ` https://api.demdex.com/...`  |
|  **Beta** | ` https://api-beta.demdex.com/...`  |


>[!NOTE]
>
>The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.



## Versions {#section_473AE7014EE949E7AD868AB357452673}

New versions of these APIs are released on a regular schedule. A new release increments the API version number. The version number is referenced in the request URL as ` v<version number>` as shown in the following example: 

` https:// <host>/v1/...` 
