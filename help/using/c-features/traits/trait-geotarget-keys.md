---
description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting With Platform-level Keys
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
index: y
internal: n
snippet: y
---

# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.

<!-- 

c_tb_platform_vars.xml

 -->

This topic contains the following sections:

* [Purpose of Platform-level Variables](../../c-features/traits/trait-geotarget-keys.md#section_57C422B2079C480B907279D5B57A6AEF) 
* [Adding Values to Platform Level Keys](../../c-features/traits/trait-geotarget-keys.md#section_1BAF23A099FF40CEB67DFC330BCB8D53) 
* [User Defined Platform-Level Keys](../../c-features/traits/trait-geotarget-keys.md#section_532CE169CFF648BCABEF17A7B0EF1C8C) 
* [Platform Level Keys Defined by IP Address](../../c-features/traits/trait-geotarget-keys.md#section_C1CCBD2C225F4E898CEE01613899B775)

## Purpose of Platform-level Variables {#section_57C422B2079C480B907279D5B57A6AEF}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#section_1BAF23A099FF40CEB67DFC330BCB8D53}

For some platform-level keys, you can specify the value yourself. With others, the keys are associated with corresponding IP addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#section_532CE169CFF648BCABEF17A7B0EF1C8C}

You specify the value when building traits with these key-value pairs:  

|  Key  | For Targeting  |
|---|---|
| `d_zx`  |ZIP code (e.g., `d_zx=10022`).  |

## Platform Level Keys Defined by IP Address {#section_C1CCBD2C225F4E898CEE01613899B775}

The values for these keys are determined by matching IP addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

<table id="table_E6E5AEC959D644C698C508775E883BAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> For Targeting </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_area_code</span> </td> 
   <td colname="col2"> <p><a href="https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes" format="https" scope="external"> North America area codes</a>. </p> <p>For example: 
     <ul class="simplelist"> 
      <li><b>Trait: </b><span class="codeph"> d_area_code=801</span> </li> 
      <li><b>Trait Name: </b>Utah </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_city</span> </td> 
   <td colname="col2"> <p>Cities and towns. Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/d_city.txt" scope="external" format="https"> City List</a>. </p> <p>For example: </p> <p> 
     <ul class="simplelist"> 
      <li><b>Trait: </b><span class="codeph"> d_city=bonn</span> </li> 
      <li><b>Trait Name: </b>Bonn </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_country</span> </td> 
   <td colname="col2"> <p>Values correspond to ISO country codes. For a searchable list of codes, see the ISO <a href="https://www.iso.org/obp/ui/#home" format="https" scope="external"> Online Browsing Platform</a>. </p> <p>Targeting for the United Kingdom is the only special case that does not obey ISO 3166. You should use "UK" instead of "GB" for targeting in the United Kingdom. </p> <p>To target the Netherlands Antilles, the code "AN" has been deprecated since 2010. The area has been dissolved into five separate territorial units. The implication is that for targeting in the Netherlands Antilles, you should not use "AN," but a combination of the country codes for "CW," "SX," and "BQ." </p> <p>For example: </p> <p> 
     <ul class="simplelist"> 
      <li><b>Trait: </b><span class="codeph"> d_country=CZ</span> </li> 
      <li><b>Trait Name: </b>Czech Republic </li> 
      <li><b>Trait: </b><span class="codeph"> d_country=UK</span> </li> 
      <li><b>Trait Name: </b>United Kingdom </li> 
      <li><b>Trait: </b><span class="codeph"> d_country=CW OR d_country=SX OR d_country=BQ</span> </li> 
      <li><b>Trait Name: </b>Netherlands Antilles </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_dma_code</span> </td> 
   <td colname="col2"> <p>Metropolitan area DMA codes. Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/DMAregions.csv" format="https" scope="external"> DMA region list</a> (.csv format). </p> <p>For example: </p> <p> 
     <ul class="simplelist"> 
      <li><b>Trait: </b><span class="codeph"> d_dma_code=807</span> </li> 
      <li><b>Trait Name: </b>San Francisco </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_lat</span> </td> 
   <td colname="col2"> <p>Latitude (e.g. <span class="codeph"> d_lat=40.75</span>). Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/d_lat.txt" format="https" scope="external"> latitudes list</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_long</span> </td> 
   <td colname="col2"> <p>Longitude (e.g. <span class="codeph"> d_long=73.98</span>). Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/d_long.txt" format="https" scope="external"> longitudes list</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_postal_code</span> </td> 
   <td colname="col2"> <p>ZIP codes (exclude the extended +4 code). Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/d_postal_code.txt" format="https" scope="external"> postal codes list</a>. </p> <p>For example: </p> <p> 
     <ul class="simplelist"> 
      <li><b>Trait: </b><span class="codeph"> d_postal_code=84004</span> </li> 
      <li><b>Trait Name: </b>Alpine </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_state</span> </td> 
   <td colname="col2"> <p>2-character abbreviation for a US state. Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/d_state.txt" format="https" scope="external"> states codes list</a>. </p> <p>For example: </p> <p> 
     <ul class="simplelist"> 
      <li><b>Trait: </b><span class="codeph"> d_state=NY</span> </li> 
      <li><b>Trait Name:</b> New York </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_region</span> </td> 
   <td colname="col2"> <p>Regional alphanumeric IDs. Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/Country_RegionCodes_City.csv" format="https" scope="external"> region list</a>. </p> <p>Then, you can use <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/region_codes_names.csv" format="https" scope="external"> this list</a> to match region IDs to region names. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_isp</span> </td> 
   <td colname="col2"> <p>ISP/organization. Download the <a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/d_isp.txt" format="https" scope="external"> ISP List</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

The list of [all location-based signals](https://marketing.adobe.com/resources/help/en_US/aam/downloads/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long` 

>[!MORE_LIKE_THIS]
>
>* [Prefix Requirements for Key Variables](../../c-features/traits/trait-variable-prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC)
