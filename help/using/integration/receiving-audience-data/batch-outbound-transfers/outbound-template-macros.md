---
description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Outbound Template Macros
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
---

# Outbound Template Macros {#outbound-template-macros}

Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.

## File Name and File Header Macros {#section_B070DE5085CE4E65AA2B815F681890C7}

The table lists and describes the macros you can use in the file name and to define header fields. For code samples, see [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
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
   <td colname="col2"> <p>Data provider ID. </p> </td> 
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
   <td colname="col2"> <p>An alias for an order / destination ID. </p> <p>The alias is set in the admin UI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_MODE </span> </p> </td> 
   <td colname="col2"> <p>Indicates synchronization type and includes: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <span class="codeph"> full </span>: Full synchronization. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <span class="codeph"> iter </span>: Incremental synchronization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_TYPE </span> </p> </td> 
   <td colname="col2"> <p>Indicates data transfer method and includes: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <span class="codeph"> ftp </span> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <span class="codeph"> http </span> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <span class="codeph"> s3 </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TAB </span> </p> </td> 
   <td colname="col2"> <p>Used as a separator, this macro inserts a tab between fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TIMESTAMP </span> </p> </td> 
   <td colname="col2"> <p>A 10-digit, UTC, Unix timestamp. </p> <p>It can also be formatted as <span class="codeph"> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </span> following Java date/timestamp formatting rules. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Content Macros {#section_A32C5FE93FEF492A80C09047E5F53272}

Macros used to format the contents of a data file. For code samples, see [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> CLOSE_CURLY_BRACKET </span> </p> </td> 
   <td colname="col2"> <p>Inserts a close curly bracket } character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID </span> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Data Provider Unique User Identifier </span>. </p> <p>This is the ID for the data partner you send data to in an outbound file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list that contains multiple IDs for a data partner. This is useful if you have a large organization with multiple subdivisions or other organizational groups you're allowed to share data with. This macro returns a list of the IDs for those subordinate groups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DPID </span> </p> </td> 
   <td colname="col2"> <p>Data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DPUUIDS </span> </p> </td> 
   <td colname="col2"> <p>The output of this macro maps the data provider ID (DPID) to related unique user IDs (DPUUID). This macro must have a formatting string to control its output. Sample output would look similar to the following: </p> <p> <span class="codeph"> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </span> </p> <p>The <span class="codeph"> maxMappings </span> setting determines how many mappings you want the macro to return. When <span class="codeph"> maxMappings=0 </span>, this macro returns all the mappings for each specified DPID. Data is sorted by timestamp (most recent first) and returns results with the largest timestamp first. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </span> </p> </td> 
   <td colname="col2"> <p>This combination of macros creates a conditional statement that lists the segments users belong to and have been removed from. It returns an empty string if both conditions are not met or there's no data. </p> </td> 
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
   <td colname="col1"> <p> <span class="codeph"> ORDER_ID </span> </p> </td> 
   <td colname="col2"> <p>Order or destination ID. </p> </td> 
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
   <td colname="col2"> <p>Partner ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> PIDALIAS </span> </p> </td> 
   <td colname="col2"> <p>An alias for an order / destination ID. </p> <p>The alias is set in the admin UI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list of segments, if any, that have been removed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list of segments in a list. Accepts the following optional arguments: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <span class="codeph"> segmentId </span>: Segment ID. Deprecated. Use <span class="codeph"> sid </span>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <span class="codeph"> csegid </span>: Customer segment ID. Deprecated. Use <span class="codeph"> sid </span>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <span class="codeph"> sid </span>: Segment ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <span class="codeph"> type </span>: Returns <span class="codeph"> 5 </span>, a static, hardcoded value that identifies data as segment data. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <span class="codeph"> alias </span>: Deprecated. Do not use. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <span class="codeph"> lastUpdateTime </span>: A Unix time stamp that indicates the last time a segment was realized. </li> 
    </ul> <p>Put these variables in curly brackets after the macro. For example, this code separates results with a pipe "|" character: <span class="codeph"> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SET_ATTRIBUTES </span> </p> </td> 
   <td colname="col2"> <p>Returns <span class="codeph"> 1 </span>, as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_MODE </span> </p> </td> 
   <td colname="col2"> <p>Indicates synchronization type and includes: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <span class="codeph"> full </span>: Full synchronization. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <span class="codeph"> iter </span>: Incremental synchronization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SYNC_TYPE </span> </p> </td> 
   <td colname="col2"> <p>Indicates data transfer method and includes: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <span class="codeph"> ftp </span> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <span class="codeph"> http </span> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <span class="codeph"> s3 </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TAB </span> </p> </td> 
   <td colname="col2"> <p>Used as a separator, this macro inserts a tab between fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TRAIT_LIST </span> </p> </td> 
   <td colname="col2"> <p>Returns a list of traits. Accepts the following optional arguments: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <span class="codeph"> type </span>: Identifies trait types by numeric ID. Returns: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <span class="codeph"> 10 </span> which identifies a DPM trait (offline, onboarded by an inbound job). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <span class="codeph"> 3 </span> which identifies a rules-based trait (realtime, onboarded through the DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <span class="codeph"> traitId </span>: trait ID. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <span class="codeph"> lastRealized </span>: The last time the trait was realized. Unix time stamp. </li> 
    </ul> <p>Put these variables in curly brackets after the macro. For example, this code separates the results with a pipe "|" character: <span class="codeph"> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> UUID </span> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> user ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)
