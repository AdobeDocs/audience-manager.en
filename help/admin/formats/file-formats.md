---
description: Lists the macros you can use to create FTP-based data files. Some macros can be used for all data file fields and rows. Other macros are specific to header and data rows only.
seo-description: Lists the macros you can use to create FTP-based data files. Some macros can be used for all data file fields and rows. Other macros are specific to header and data rows only.
seo-title: File Format Macros
title: File Format Macros
uuid: f91c91b6-6581-4ed7-8d7f-f8532bd41df9
index: y
internal: n
snippet: y
---

# File Format Macros{#file-format-macros}

Lists the macros you can use to create FTP-based data files. Some macros can be used for all data file fields and rows. Other macros are specific to header and data rows only.

Contents:

<ul class="simplelist"> 
 <li> <a href="../formats/file-formats.md#section_B8C6F1B0605E48EABABBB29AD5A08A67" format="dita" scope="local"> Common Macros </a> </li> 
 <li> <a href="../formats/file-formats.md#section_88196DDAECD543599DE232CE24613771" format="dita" scope="local"> Header Field Macros </a> </li> 
 <li> <a href="../formats/file-formats.md#section_816D21F068FB492A8BA0B96525D9D504" format="dita" scope="local"> Data Row Macros </a> </li> 
</ul>

## Common Macros {#section_B8C6F1B0605E48EABABBB29AD5A08A67}

These macros can be used in any format field. For examples, see [File Format Macro Examples](../formats/file-format-examples.md#concept_375D892B7A5C4B699FA7D6B0908D76F8).

<table id="table_A3309E175ABF4651BD11CE3632B3C553"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ASCII_SOH </span> </p> </td> 
   <td colname="col2"> <p>A non-printing ASCII character. It indicates the start of a row or a section of content. It can also be used to separate data columns in a file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DPID </span> </p> </td> 
   <td colname="col2"> <p>Target Data Provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> MASTER_DPID </span> </p> </td> 
   <td colname="col2"> <p>User ID Key Data Provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ORDER_ID </span> </p> </td> 
   <td colname="col2"> <p>Order / destination ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> PIDALIAS </span> </p> </td> 
   <td colname="col2"> <p>An alias for an order / destination ID. </p> <p>The value for this alias is set in the <span class="wintitle"> Foreign Account ID </span> field for a destination (in the <span class="wintitle"> Basic Settings </span> section). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_MODE </span> </p> </td> 
   <td colname="col2"> <p>Indicates synchronization type. Accepts the following optional variables: </p> 
    <ul id="ul_87E8E3CE6565447A9810B5119298CC7B"> 
     <li id="li_66F4889FB84E40AC92F69F3FF6B0042C"> <span class="codeph"> full </span>: Full synchronization. </li> 
     <li id="li_BFE2C2D9A33A44FB9A840A7232ECCFFF"> <span class="codeph"> iter </span>: Incremental synchronization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_TYPE </span> </p> </td> 
   <td colname="col2"> <p>Indicates data transfer method. Accepts the following optional variables: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <span class="codeph"> ftp </span> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <span class="codeph"> http </span> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <span class="codeph"> s3 </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TIMESTAMP </span> </p> </td> 
   <td colname="col2"> <p>A 10-digit, UTC, Unix timestamp. </p> <p>It can also be formatted as <span class="codeph"> YYYYMMDDhhmmss </span> following Java date/timestamp formatting rules. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header Field Macros {#section_88196DDAECD543599DE232CE24613771}

Macros used in header fields only. For examples, see [File Format Macro Examples](../formats/file-format-examples.md#concept_375D892B7A5C4B699FA7D6B0908D76F8).  

<table id="table_1A8BD1750F4940B3A34E3F80371A447A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TAB </span> </p> </td> 
   <td colname="col2"> <p>Used as a separator, this macro inserts a tab between fields. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Data Row Macros {#section_816D21F068FB492A8BA0B96525D9D504}

Macros used in data rows only. For examples, see [File Format Macro Examples](../formats/file-format-examples.md#concept_375D892B7A5C4B699FA7D6B0908D76F8) .

<table id="table_E378F94A3907407AA8110C8EE6C10909"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> CLOSE_CURLY_BRACKET </span> </p> </td> 
   <td colname="col2"> <p>Inserts a closed curly bracket } character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> COMMA </span> </p> </td> 
   <td colname="col2"> <p>Inserts a comma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID </span> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Data Partner Unique User Identifier </span>. Returns the ID you've assigned to a user/site visitor if that ID has already been synchronized with an <span class="keyword"> Audience Manager </span> device ID. </p> <p>If the DPID is 0, this macro will return the <span class="keyword"> Audience Manager </span> ID instead of your ID for the user. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list that contains multiple IDs for a data partner. This is useful if you have a large organization with multiple subdivisions or other organizational groups you're allowed to share data with. This macro returns a list of the IDs for those subordinate groups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DPUUIDS </span> </p> </td> 
   <td colname="col2"> <p>The output of this macro maps the data provider ID (DPID) to related unique user IDs (DPUUID). This macro must have a formatting string to control its output. Sample output would look similar to the following: </p> <p> <span class="codeph"> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </span> </p> <p>The <span class="codeph"> maxMappings </span> setting determines how many mappings you want the macro to return. When <span class="codeph"> maxMappings=0 </span>, this macro returns all the mappings for each specified DPID. Data is sorted by timestamp (most recent first) and returns results with the largest timestamp first. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> endif </span> </p> </td> 
   <td colname="col2"> <p>Required when using the conditional <span class="codeph"> if </span> and the <span class="codeph"> SEGMENT_LIST </span> and <span class="codeph"> REMOVED_SEGMENT_LIST </span> macros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </span> </p> </td> 
   <td colname="col2"> <p>This combination of macros creates a conditional statement that lists the segments users belong to <i>and</i> have been removed from. It returns an empty string if both conditions are not met or there's no data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> MCID </span> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> OPEN_CURLY_BRACKET </span> </p> </td> 
   <td colname="col2"> <p>Inserts an open curly bracket { character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> OPT_OUT </span> </p> </td> 
   <td colname="col2"> <p>Deprecated. Do not use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> OUTPUT_ATTRIBUTE_TYPE </span> </p> </td> 
   <td colname="col2"> <p>Deprecated. Do not use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> OUTPUT_ATTRIBUTE_VALUE </span> </p> </td> 
   <td colname="col2"> <p>Returns <span class="codeph"> 1 </span> as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> PID </span> </p> </td> 
   <td colname="col2"> <p>Partner ID (PID). The PID appears under the <span class="wintitle"> Profile </span> tab in the admin UI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list of segments, if any, that have been removed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list of segments in a list. Accepts the following optional variables: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <span class="codeph"> segmentId </span>: Legacy ID. Deprecated. Use <span class="codeph"> sid </span> (lower case only). </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <span class="codeph"> csegid </span>: Legacy ID. Deprecated. Use <span class="codeph"> sid </span> (lower case only). </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <span class="codeph"> sid </span>: Segment ID. </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <span class="codeph"> type </span>: Returns <span class="codeph"> 5 </span>, a static, hardcoded value that identifies data as segment data. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <span class="codeph"> alias </span>: Mapping of the segment. Deprecated. Use <span class="codeph"> sid </span> (lower case only). </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <span class="codeph"> lastUpdateTime </span>: A Unix time stamp that indicates the last time a segment was realized. </li> 
    </ul> <p>Put these variables in curly brackets after the macro. For example, this code separates results with a pipe "|" character: <span class="codeph"> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator="|"&gt; </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SET_ATTRIBUTES </span> </p> </td> 
   <td colname="col2"> <p>Returns <span class="codeph"> 1 </span> as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TAB </span> </p> </td> 
   <td colname="col2"> <p>Inserts a tab separator. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TRAIT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list of traits. Accepts the following optional arguments: </p> 
    <ul id="ul_757DEB56E4F849768468F3C166B0D171"> 
     <li id="li_859E1F4F21D645519F150DC512B3EB1A"> <span class="codeph"> type </span>: Trait types identified by a numeric ID. This variable returns: 
      <ul id="ul_C9839266783D42CCADAAC3FEA33BE4D7"> 
       <li id="li_6996A218E3F04EC3BC70032559DD87FC"> <span class="codeph"> 10 </span> which identifies a DPM trait (offline, onboarded by an inbound job). </li> 
       <li id="li_831FF929BF50434C8804C13E5786DF79"> <span class="codeph"> 3 </span> which identifies a rules-based trait (realtime,; onboarded through the <span class="wintitle"> DCS </span>). </li> 
      </ul> </li> 
     <li id="li_E84D6BC80AEE4F10963C9882C4151ED4"> <span class="codeph"> traitId </span>: Trait ID. </li> 
     <li id="li_D30A849BA35248E6B9110FA3ADEFC332"> <span class="codeph"> lastRealized </span>: Last time the trait was realized. Unix timestamp. </li> 
    </ul> <p>Put these variables in curly brackets after the macro. For example, this code separates the results with a pipe "|" character: <span class="codeph"> TRAIT_LIST{type|traitId};separator="|" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> UUID </span> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> user ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

