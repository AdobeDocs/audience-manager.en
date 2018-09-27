---
description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formatting Key-Value Pairs in DCS Calls
uuid: 749e7b3d-aa7f-4cb2-9051-4ac41acaea8f
index: y
internal: n
snippet: y
translate: y
---

# Formatting Key-Value Pairs in DCS Calls

When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.



## Standard and Serialized Key-Value Pairs {#section_ED54A051F8CD43798C50CAFA438D6B51}





<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key-Value Type </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Example </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>A standard key-value pair consists of a single key and value. This structure organizes data into separate key-value pairs. Each key is stated explicitly, even when it’s used again to define a different value. This is the most common way to send data to the <span class="wintitle"> DCS</span>. </p> </td> 
   <td colname="col3"> <span class="codeph"> key1=val1&amp;key2=val2&amp;key3=val3</span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Serialized</b> </td> 
   <td colname="col2"> <p>A serialized key-value pair consists of a single key and multiple values. This can be an efficient way to organize data, but serialized key-value pairs require specific symbols to separate each key and each key-value set. </p> </td> 
   <td colname="col3"> <span class="codeph"> key1=val1,val2,val3</span> </td> 
  </tr> 
 </tbody> 
</table>


## Delimiters and Separators for Serialized Key-Value Pairs {#section_81AE5DBD34D64B6ABF40521FCA0C9733}



With serialized key-value pairs, you must specify the markers that separate values within and between these variables. Audience Manager requires the following delimiters and separators: 




<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requirements for </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Separates Individual </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimiters</b> </td> 
   <td colname="col2"> Ampersand &amp; </td> 
   <td colname="col3"> <p>Key-value pairs: </p> <p><span class="codeph"> key1=val1&amp;key2=val2,val3</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separators</b> </td> 
   <td colname="col2"> Comma , </td> 
   <td colname="col3"> <p>Values within key-value pairs: </p> <p><span class="codeph"> key1=val1,val2,val3&amp;key2=valA,valB,valC</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Send Data to the DCS](dcs-url-send.md#concept_9F6C569C1E444002ADF2A43516A9F284)
>* [Key-Value Prefixes and Variables Supported by the DCS](dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5)
>* [Key-Value Pairs Explained](key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)
