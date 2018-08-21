---
description: Describes the required fields, syntax, and conventions used to organize information in an outbound data file. Format your data according to these specifications.
seo-description: Describes the required fields, syntax, and conventions used to organize information in an outbound data file. Format your data according to these specifications.
seo-title: Outbound Data File Contents  Syntax and Parameters
solution: Audience Manager
title: Outbound Data File Contents  Syntax and Parameters
uuid: d954f098-489a-48fd-a862-0baa20478244
index: y
internal: n
snippet: y
translate: y
---

# Outbound Data File Contents: Syntax and Parameters

Note: The style elements ( ` monospace text`, *italics*, brackets [ ] ( ), etc.) in this document indicate code elements and options. See [ Style Conventions for Code and Text Elements ](../../../c_reference/code-style-elements.md#reference_59D0BD0EDB424A65853460D91CCA35D9) for more information. 

**Syntax** 

Fields in the data file appear in this order: 

` *` UUID`*<SPACE> *` SEGMENT_1,SEGMENT_2`*<SPACE> *` REMOVED_SEGMENT_1`*,...` 

**Parameters** 

The table lists variables that define the contents of a data file. 



<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> UUID </span> </span> </p> </td> 
   <td colname="col2"> <p>A unique user ID assigned by Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;SPACE&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p>Separate the UUID and segment data with a space </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> SEGMENT_N </span> </span> </p> </td> 
   <td colname="col2"> <p>The segment ID that a visitor belongs to. Separate multiple segments with a comma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_SEGMENT_N </span> </p> </td> 
   <td colname="col2"> <p>The segment ID from which the user was disqualified. Separate multiple segments with a comma. With a full synchronization, you can ignore the removed segments because the data file will contain the complete list of current segments for the user. Usually, you want to know about segments a user belongs to rather than those they've been removed from. See also <a href="../../../c_integration/c_outbounding_data/c_outbound_intro/c_name_reqs_outbound.md#concept_C049B849113544CA92EC194A60D0F722" format="dita" scope="local"> Outbound Data File Name: Syntax and Examples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example: Basic File Format** 

A properly formatted data file could look similar to the following sample. This file entry indicates a user qualifies for segments 24, 26, and 27. As required, a space separates the UUID and segment IDs. Another space separates the sets of segment IDs. In this example, a user belongs to segments 24, 26, and 27. They've been removed from segments 25 and 28. 


```
59767559181262060060278870901087098252  24,26,27  25,28
```

