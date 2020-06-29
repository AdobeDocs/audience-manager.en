---
description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formatting Key-Value Pairs in DCS Calls
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
---

# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!DNL DCS] accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.

## Standard and Serialized Key-Value Pairs {#standard-serialized}

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
   <td colname="col2"> <p>A standard key-value pair consists of a single key and value. This structure organizes data into separate key-value pairs. Each key is stated explicitly, even when it’s used again to define a different value. This is the most common way to send data to the DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serialized</b> </td> 
   <td colname="col2"> <p>A serialized key-value pair consists of a single key and multiple values. This can be an efficient way to organize data, but serialized key-value pairs require specific symbols to separate each key and each key-value set. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

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
   <td colname="col3"> <p>Key-value pairs: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separators</b> </td> 
   <td colname="col2"> Comma , </td> 
   <td colname="col3"> <p>Values within key-value pairs: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Key-Value Prefixes and Variables Supported by the DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Key-Value Pairs Explained](../../../reference/key-value-pairs-explained.md)
