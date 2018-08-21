---
description: Lists and defines the data structure of a Customer Data Feed (CDF) file. This includes data sequence, field delimiters and separators, a data file map, and sample file.
seo-description: Lists and defines the data structure of a Customer Data Feed (CDF) file. This includes data sequence, field delimiters and separators, a data file map, and sample file.
seo-title: Customer Data Feed File Structure
solution: Audience Manager
title: Customer Data Feed File Structure
uuid: aa87fced-2c92-48ea-a30b-2d88b608ea9b
index: y
internal: n
snippet: y
translate: y
---

# Customer Data Feed File Structure

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../c_features/cdf-intro/cdf-file-structure.md#section_FBE42884A7714114BC5D434C105BCCEF" format="dita" scope="local"> Data Field Identifiers and Sequence </a> </li> 
 <li> <a href="../../c_features/cdf-intro/cdf-file-structure.md#section_E57453FBC4D4489484F122BE75EECBDE" format="dita" scope="local"> CDF File Map </a> </li> 
 <li> <a href="../../c_features/cdf-intro/cdf-file-structure.md#section_8DD0364915C8428B8BCEF02C981779EA" format="dita" scope="local"> Sample CDF File </a> </li> 
</ul>



## Data Field Identifiers and Sequence {#section_FBE42884A7714114BC5D434C105BCCEF}

CDF files do not contain labeled columns or field headers. Instead, a CDF file defines fields and arrays with non-printing ASCII characters. Also, the CDF file lists each field and array in a specific order. Understanding the field identifiers and order will help you parse the file properly. 



<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF File Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Field Separators and Delimiters </p> </td> 
   <td colname="col2"> <p>These non-printing characters define the elements and structure of your CDF file: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <span class="codeph"> 001</span> or <span class="codeph"> ^A</span>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <span class="codeph"> 002</span> or <span class="codeph"> ^B</span>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <span class="codeph"> 003</span> or <span class="codeph"> ^C</span>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Field Sequence </p> </td> 
   <td colname="col2"> <p> <p type="important">Note: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. This means the technical design of your file parsing system should not assume a fixed number of columns (though it may assume a fixed order for existing columns). </p> </p> <p>Data in your CDF file appears in the order shown below. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Event Time </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Container ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Realized Traits </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Realized Segments </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Request Parameters </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP Address </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud Device ID (or MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">All Segments </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">All Traits </li> 
     </ol> </p> <p>For field descriptions, see <a href="../../c_features/cdf-intro/cdf-contents-defined.md#reference_6257ACA5665D4820900F111CFED50866" format="dita" scope="local"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


## CDF File Map {#section_E57453FBC4D4489484F122BE75EECBDE}

CDF file data appears in the order shown below. 

![](assets/sequence-map.png) 

**Identifying Arrays** 

Arrays in a CDF file start and end with the ` Ctrl + a` field separator. This makes the first element in an array appear like a standalone data field. For example, the realized traits array starts with ` ^A1234`. The array delimiter and ID ` ^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with ` ^B`). This is not the case, which is why you need to be familiar with the sequence and structure of a data file. Even though the first element in the realized trait array (or any of the other arrays in a CDF file) starts with ` ^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by ` ^A`. 

## Sample CDF File {#section_8DD0364915C8428B8BCEF02C981779EA}

A sample CDF file could look similar to the following. We've inserted line breaks into this example to help it fit the page. 

![](assets/CDF-sample.png) 
>[!MORE_LIKE_THIS]
>
>* [ Customer Data Feed Contents Defined ](cdf-contents-defined.md#reference_6257ACA5665D4820900F111CFED50866)
>* [ Customer Data Feed File Name Times and File Content Times... ](cdf-time-differences.md#concept_C907608AC1ED44BA8EF870F45E5A9CB9)
>* [ Customer Data Feed FAQ ](cdf-faq.md#concept_E832A7307FA0475C918F95116C21CBC6)
