---
description: Defines and describes standard and serialized key-value pairs.
keywords: integration code
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Key-Value Pairs Explained
uuid: 582ac81f-b06b-4b13-a74c-ccf535d3e522
index: y
internal: n
snippet: y
translate: y
---

# Key-Value Pairs Explained

A key-value pair consists of two related data elements: A key, which is a constant that defines the data set (e.g., gender, color, price), and a value, which is a variable that belongs to the set (e.g., male/female, green, 100). Fully formed, a key-value pair could look like these: 

* ` gender = male`
* ` color = green`
* ` price > 100`
The following sections contain more information: 

* [ Standard and Serialized Key-Value Pairs ](../c_reference/c_key_value_explained.md#section_8EB30E223EE2482693933012418CC842)
* [ Keys, Delimiters, and Separators ](../c_reference/c_key_value_explained.md#section_BF135864D25C43DCB19B871A4CD6B202)
* [ Standard and Serialized Key-Value Elements ](../c_reference/c_key_value_explained.md#section_54E6025C5B8E497B918BF2F6A8DC8042)

## Standard and Serialized Key-Value Pairs {#section_8EB30E223EE2482693933012418CC842}

Destinations accept key-value data in *` standard`* or *` serialized`* format. Standard formatting organizes data into separate key-value pairs. Each key is stated explicitly, even when used again to define a different value. By contrast, serialized formatting condenses multiple values into one set defined by a single key. Also, in a serialized pair, a special indicator is used to separate the values within the key-value set. Finally, standard and serialized key-values can contain single or multiple values. The following table provides examples of standard and serial key-value formats. 

|  Formatting  | Single Key  | Key-Value Pairs  |
|---|---|---|
|  **Standard** | ` x=1&x=2`  | ` x=1&amp;x=2&amp;y=3&amp;y=4`  |
|  **Serialized** | ` x=1;2`  | ` x=1;2&amp;y=3;4`  |

**** 

## Keys, Delimiters, and Separators {#section_BF135864D25C43DCB19B871A4CD6B202}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Elements in key-value pairs are defined as follows: 

* **Key:** A unique identifier in the key-value pair.
* **Value delimiter:** Separates individual key-value pairs.
* **Key-value separator:** Separates a key from the values within a key-value pair.
* **Serial separator:** Separates individual values within serialized key-value pairs.

## Standard and Serialized Key-Value Elements {#section_54E6025C5B8E497B918BF2F6A8DC8042}


<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Example </th> 
   <th colname="col3" class="entry"> Key </th> 
   <th colname="col4" class="entry"> Key-Value Separator </th> 
   <th colname="col5" class="entry"> Key-Value Delimiter </th> 
   <th colname="col6" class="entry"> Serial Separator </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Single key</b> <p>(standard) </p> </td> 
   <td colname="col2"> <span class="codeph"> x=1&amp;amp;x=2 </span> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp;amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Key-value pairs</b> <p>(standard) </p> </td> 
   <td colname="col2"> <span class="codeph"> x=1&amp;amp;x=2&amp;amp;y=3&amp;amp;y=4 </span> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Single key</b> <p>(serial) </p> </td> 
   <td colname="col2"> <span class="codeph"> x=1;2;3 </span> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Key-value pairs</b> (serial) </td> 
   <td colname="col2"> <span class="codeph"> x=1;2&amp;amp;y=3;4 </span> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp;amp; </td> 
  </tr> 
 </tbody> 
</table>

