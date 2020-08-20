---
description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Outbound Template Macros
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
---

# Outbound Template Macros {#outbound-template-macros}

Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.

## File Name and File Header Macros {#file-name-header-macros}

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
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>A non-printing ASCII character. It indicates the start of a row or a section of content. It can also be used to separate data columns in a file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>User ID Key Data Provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Allows the creation of multi-line headers for outbound orders. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Order / destination ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>An alias for an order / destination ID. </p> <p>The alias is set in the admin UI. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indicates the splitting of outbound files into multiple parts. Replace the SPLITNUM section in the file name with the part number preceded by zeros, ensuring a minimum of three characters for the SPLITNUM section.</p>
   <p>The SPLITNUM macro does not need to be surrounded by <> characters.</p><p>Example: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>The last three digits (001,002,003) in the examples above are the SPLITNUM identifiers.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indicates synchronization type and includes: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Full synchronization. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Incremental synchronization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indicates data transfer method and includes: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Used as a separator, this macro inserts a tab between fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>A 10-digit, UTC, Unix timestamp. </p> <p>It can also be formatted as <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> following Java date/timestamp formatting rules. </p> </td> 
  </tr>
  
 </tbody> 
</table>

## Content Macros {#content-macros}

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
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserts a close curly bracket <code>}</code> character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Data Provider Unique User Identifier </span>. </p> <p>This is the ID for the data partner you send data to in an outbound file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returns a list that contains multiple IDs for a data partner. This is useful if you have a large organization with multiple subdivisions or other organizational groups you're allowed to share data with. This macro returns a list of the IDs for those subordinate groups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>The output of this macro maps the data provider ID (DPID) to related unique user IDs (DPUUID). This macro must have a formatting string to control its output. Sample output would look similar to the following: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>The <code> maxMappings </code> setting determines how many mappings you want the macro to return. When <code> maxMappings=0 </code>, this macro returns all the mappings for each specified DPID. Data is sorted by timestamp (most recent first) and returns results with the largest timestamp first. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>This combination of macros creates a conditional statement that lists the segments users belong to and have been removed from. It returns an empty string if both conditions are not met or there's no data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserts an open curly bracket <code>{</code> character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Deprecated. Do not use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Order or destination ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Deprecated. Do not use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Returns <code> 1 </code> as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>Partner ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>An alias for an order / destination ID. </p> <p>The alias is set in the admin UI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returns a list of segments, if any, that have been removed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returns a list of segments in a list. Accepts the following optional arguments: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: Segment ID. Deprecated. Use <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: Customer segment ID. Deprecated. Use <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: Segment ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Returns <code> 5 </code>, a static, hardcoded value that identifies data as segment data. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Deprecated. Do not use. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: A Unix time stamp that indicates the last time a segment was realized. </li> 
    </ul> <p>Put these variables in curly brackets after the macro. For example, this code separates results with a pipe "|" character: <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Returns <code> 1 </code>, as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indicates synchronization type and includes: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Full synchronization. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Incremental synchronization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indicates data transfer method and includes: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Used as a separator, this macro inserts a tab between fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returns a list of traits. Accepts the following optional arguments: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifies trait types by numeric ID. Returns: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> which identifies a DPM trait (offline, onboarded by an inbound job). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> which identifies a rules-based trait (realtime, onboarded through the DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: trait ID. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: The last time the trait was realized. Unix time stamp. </li> 
    </ul> <p>Put these variables in curly brackets after the macro. For example, this code separates the results with a pipe "|" character: <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> user ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)
