---
description: Examples of how macros are used to create outbound, FTP file templates.
seo-description: Examples of how macros are used to create outbound, FTP file templates.
seo-title: File Format Macro Examples
title: File Format Macro Examples
uuid: f00d431d-7e43-457a-b633-c79cbc4c8f10
index: y
internal: n
snippet: y
---

# File Format Macro Examples{#file-format-macro-examples}

Examples of how macros are used to create outbound, FTP file templates.

Contents:

<ul class="simplelist"> 
 <li> <a href="../formats/file-format-examples.md#section_65E394A8A471425CAF8803834F51DE93" format="dita" scope="local"> Common Macros </a> </li> 
 <li> <a href="../formats/file-format-examples.md#section_96958B51FC8D49F48C773ECA410F8D67" format="dita" scope="local"> Header Field Macros </a> </li> 
 <li> <a href="../formats/file-format-examples.md#section_EFD1F85D181A4F9E8CF65F5386EAC438" format="dita" scope="local"> Data Row Macros </a> </li> 
</ul>

>[!NOTE]
>
>In the tables, **boldface** type identifies each macro with its related output. For the format examples, the < > symbols have been added to help visually separate each macro.

## Common Macros {#section_65E394A8A471425CAF8803834F51DE93}

These macros can be used in any format field. See the [File Format Macros](../formats/file-formats.md#concept_A867101505074418A58DE325949E5089) for a complete list and definitions.

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Format and Output Examples </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DPID </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </span> </p> <p>Output: <span class="codeph"> ftp_215_ 888_iter_1449756724.sync </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> MASTER_DPID </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </span> </p> <p>Output: <span class="codeph"> ftp_215_888_ 20915_iter_1449756724.sync </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ORDER_ID </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </span> </p> <p>Output: <span class="codeph"> ftp_ 215_888_iter_1449756724.sync </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_MODE </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </span> </p> <p>Output: 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Full: <span class="codeph"> ftp_215_888_ full_1449756724.sync </span> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incremental: <span class="codeph"> ftp_215_888_ iter_1449756724.sync </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_TYPE </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </span> </p> <p>Output: 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <span class="codeph"> ftp_215_888_iter_1449756724.sync </span> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <span class="codeph"> http_215_888_iter_1449756724.sync </span> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <span class="codeph"> s3_215_888_iter_1449756724.sync </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TIMESTAMP </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;.sync </span> </p> <p>Output: <span class="codeph"> ftp_215_888_iter_ 1449756724.sync </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header Field Macros {#section_96958B51FC8D49F48C773ECA410F8D67}

Macros used in header fields only. See the [File Format Macros](../formats/file-formats.md#concept_A867101505074418A58DE325949E5089) for a complete list and definitions.

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Format and Output Examples </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TAB </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </span> </p> <p>Output: <span class="codeph"> 888 full.sync </span> </p> <p>In the output, the non-printing tab character separates each element. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Data Row Macros {#section_EFD1F85D181A4F9E8CF65F5386EAC438}

Macros used in header fields only. See the [File Format Macros](../formats/file-formats.md#concept_A867101505074418A58DE325949E5089) for a complete list and definitions.

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Format and Output Examples </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </span> </p> <p>Output: <span class="codeph"> 123456 UUID1 UUID2 UUID3 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID_LIST </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </span> </p> <p>Output: <span class="codeph"> 123456 UUID1 UUID2 UUID3 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p>This example creates a format that returns removed segments in a server-to-server feed. </p> <p> 
     <codeblock>
       {"AdvertiserId":"&lt;PIDALIAS&gt;",&nbsp;"DataCenterId":&nbsp;2,"TDID":"&lt;DP_UUID&gt;", 
      
"Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;"&lt;CLOSE_CURLY_BRACKET&gt;}; 
      
separator=","&gt;&lt;if(SEGMENT_LIST&nbsp;&amp;&amp;&nbsp;REMOVED_SEGMENT_LIST)&gt;&lt;COMMA&gt;&lt;endif&gt; 
      
&lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;", 
      
"TtlInMinutes":0&lt;CLOSE_CURLY_BRACKET&gt;};&nbsp;separator=","&gt;]} 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;DP_UUID&gt; &lt;SEGMENT_LIST&gt;;separator=" "&gt; </span> </p> <p>Output: <span class="codeph"> 123456 105955 101183 101180 101179 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SET_ATTRIBUTES </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt; &lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;OPT_OUT&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastUpdateTime&gt;&amp;}&gt; </span> </p> <p>Output: <span class="codeph"> 1159 00088008579683653741516297509717335000 17t0aj01b120hp 1 0 5,103714,1,1344114661000&amp;5,103713,1,1343250661000 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TAB </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </span> </p> <p>Output: <span class="codeph"> 123456 UUID1 UUID2 UUID3 </span> </p> <p>In the output, the non-printing tab character separates each element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TRAIT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Format: <span class="codeph"> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator=“|”&gt; </span> </p> <p>Output: <span class="codeph"> 1131 12345 1 123|456|789 </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

