---
description: Lists the macros you can use to create HTTP data files. HTTP sends data in a JSON format.
seo-description: Lists the macros you can use to create HTTP data files. HTTP sends data in a JSON format.
seo-title: HTTP Format Macros
title: HTTP Format Macros
uuid: 91021f60-75d0-4b1d-86ca-91c9dadafac1
index: y
internal: n
snippet: y
---

# HTTP Format Macros{#http-format-macros}

Lists the macros you can use to create HTTP data files. HTTP sends data in a JSON format.



See the [HTTP Format Macro Examples](../formats/web-format-examples.md#reference_98828E32B0964FF9AAC7C5400E88BA31) for a list and examples of some commonly used macro combinations. 

<table id="table_72A72EA63C3643FB84B47A76CD2CC1CA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Method Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> AAM_UUID </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p> <span class="keyword"> Audience Manager </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DP_UUID </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>Data Partner Unique User ID. This macro returns the ID you’ve assigned to a user if their ID has already been synchronized with an <span class="keyword"> Audience Manager </span> device ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> DPID </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>Data Provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> GENERATION_TIME </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET, POST </span> </p> </td> 
   <td colname="col3"> <p>Unix UTC timestamp. An internal timestamp, represents the time AAM was notified to publish the <span class="wintitle"> S2S </span> destination to our partners. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> IP </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>The user's IP address. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> NUM_REMOVED_SEGMENTS </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>The number (integer) of segments a user no longer belongs to. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> NUM_SEGMENTS </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>The number of segments a user belongs to. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ORDER_ID </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET, POST </span> </p> </td> 
   <td colname="col3"> <p>Order or destination ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> PID_ALIAS </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET, POST </span> </p> </td> 
   <td colname="col3"> <p>An alias for the partner ID. Also known as Foreign Account ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> RANDOM </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>Generates a random number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>Returns a list of segment IDs, if any, that a user no longer qualifies for. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_SEGMENTS </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>A list of segments that a user no longer qualifies for. You can also return specific segment fields that include: </p> <p> 
     <ul id="ul_29B83093A7624A908F0C06F2A248981A"> 
      <li id="li_57A60A54F5D44E38ACB4E2648095F246"> <span class="codeph"> traitAlias </span> </li> 
      <li id="li_4079F646493F40DBA0CE75D662A69454"> <span class="codeph"> legacySegmentId (formerly segmentId) </span> </li> 
      <li id="li_D3509A2D379E4C1FB3BC1B5E7D45A916"> <span class="codeph"> newSegmentId </span> </li> 
      <li id="li_EA901C20EEEB4CFAA39A5E0E822D2394"> <span class="codeph"> status </span> </li> 
      <li id="li_6310E21F88CC4691980DD3C9D551409F"> <span class="codeph"> dateTime </span> </li> 
     </ul> </p> <p>Specify these fields in an array as shown in this example: </p> <p> <span class="codeph"> [&lt;REMOVED_SEGMENTS:{seg|&lt;OPEN_BRACKET&gt;"Mapping":&lt;seg.traitAlias&gt;,"Status:"&lt;seg.status&gt;, "Time":&lt;seg.dateTime&gt;,"LegacySegmentId":&lt;seg.LegacySegmentId&gt;, "NewSegmentId":&lt;seg.NewSegmentId&gt;&lt;CLOSE_BRACKET&gt;}; "separator=","&gt;] </span> </p> <p>See also <a href="../formats/web-format-examples.md#reference_98828E32B0964FF9AAC7C5400E88BA31"> HTTP Format Macro Examples </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_TIME_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> A list of last realizations for segments that the user no longer qualifies for. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> REMOVED_TRAITALIAS_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>A list of aliased names of segments that a user no longer qualifies for. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SEGMENT_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>Returns a list of segment IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> SEGMENTS </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>A list of segments a user qualifies for. You can also return specific segment fields that include: </p> <p> 
     <ul id="ul_9209683A8E0A4B8081E5EFA4602F743F"> 
      <li id="li_D796526C1C9E45BEA891D619539888C4"> <span class="codeph"> traitAlias </span> </li> 
      <li id="li_BF12E010E1AD432C84605B9817F209DD"> <span class="codeph"> legacySegmentId (formerly segmentId) </span> </li> 
      <li id="li_4A81E3B715254549B9EADB983A2FC32B"> <span class="codeph"> newSegmentId </span> </li> 
      <li id="li_1F01A60829DF4C87879D94299E1D589C"> <span class="codeph"> status </span> </li> 
      <li id="li_E52F10CD5A04487D81A4B1750B0DC4E3"> <span class="codeph"> dateTime </span> </li> 
     </ul> </p> <p>Specify these fields in an array as shown in this example: </p> <p> <span class="codeph"> [&lt;SEGMENTS:{seg|&lt;OPEN_BRACKET&gt;"Mapping":&lt;seg.traitAlias&gt;,"Status:"&lt;seg.status&gt;, "Time":&lt;seg.dateTime&gt;,"LegacySegmentId":&lt;seg.LegacySegmentId&gt;, "NewSegmentId":&lt;seg.NewSegmentId&gt;&lt;CLOSE_BRACKET&gt;}; "separator=","&gt;] </span> </p> <p>See also <a href="../formats/web-format-examples.md#reference_98828E32B0964FF9AAC7C5400E88BA31"> HTTP Format Macro Examples </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TIME_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>A list of last realizations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TIMESTAMP </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>Unix, UTC timestamp. Represents the last realization of the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TRAITALIAS_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>A list of aliased names for a particular segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> USER_AGENT </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> GET </span> </p> </td> 
   <td colname="col3"> <p>User agent of the initial request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> USER_LIST </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> POST </span> </p> </td> 
   <td colname="col3"> <p>A list of <span class="keyword"> Audience Manager </span> user IDs. You can also return specific fields that include the following: </p> 
    <ul id="ul_B6857D809FDC46749B7E745BD8C45F8E"> 
     <li id="li_F31CD82D16ED41FD82518141D90B5B35"> <span class="codeph"> user.aamUuid </span> </li> 
     <li id="li_623FA758C84D4A2D9B25C7FBE90F62B7"> <span class="codeph"> user.dpUuid </span> </li> 
     <li id="li_976B941908EB494EB476B5FB68B8972D"> <span class="codeph"> user.segments </span> </li> 
     <li id="li_D7E129833D1E4D59A554FFCE353924EE"> <span class="codeph"> user.removedSegments </span> </li> 
     <li id="li_8B3DD69D3FE3493492FC9F162812FCD5"> <span class="codeph"> user.userAgent </span> </li> 
     <li id="li_8C7EA05585A64141876DF169C31322FE"> <span class="codeph"> user.ip </span> </li> 
     <li id="li_678076A31A7743C480F718C9E7A07E99"> <span class="codeph"> user.dpuuids </span> </li> 
     <li id="li_B598A5AED28C4304972E51DBD4E480D8"> <span class="codeph"> user.timestamp </span> </li> 
     <li id="li_8424D540282F449CA5AF6B3CC343DDCB"> <span class="codeph"> user.random </span> </li> 
    </ul> <p>Specify these fields as shown in this example: </p> <p> 
     <codeblock>
       "AAM_UUID":&nbsp;"&lt;user.aamUuid&gt;" 
"DataPartner_UUID":&nbsp;"&lt;user.dpUuid&gt;" 
     </codeblock> </p> <p>See also <a href="../formats/web-format-examples.md#reference_98828E32B0964FF9AAC7C5400E88BA31"> HTTP Format Macro Examples </a> for a full example. </p> </td> 
  </tr> 
 </tbody> 
</table>

