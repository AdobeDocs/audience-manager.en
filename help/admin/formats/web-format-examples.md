---
description: Examples of some commonly used HTTP macro combinations.
seo-description: Examples of some commonly used HTTP macro combinations.
seo-title: HTTP Format Macro Examples
title: HTTP Format Macro Examples
uuid: 5f745cca-b137-4581-88a3-9d2d1f8ad175
index: y
internal: n
snippet: y
translate: y
---

# HTTP Format Macro Examples


>[ HTTP Format Macros ](../formats/web-formats.md#reference_C392124A5F3F42E49F8AADDBA601ADFE)

><table id="table_D5FAC5D056ED49D79FA883197EF8F42E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro Examples </th> 
   <th colname="col2" class="entry"> Output Format </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;PID_ALIAS&amp;gt;|&amp;lt;DP_UUID&amp;gt;|&amp;lt;TRAITALIAS_LIST; separator=","&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> pid_alias|dp_uuid|trait_1,trait_2 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;PID_ALIAS&amp;gt;|count:&amp;lt;NUM_USERS&amp;gt;|users:[&amp;lt;USER_LIST:{user|&amp;lt;user.aamUuid&amp;gt;:&amp;lt;user.dpUuid&amp;gt;}; separator=", "&amp;gt;] </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> "pid_alias|count:2|users:[uuid1:dpuuid1, uuid2:dpuuid2]" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;USER_AGENT&amp;gt;|&amp;lt;IP&amp;gt;|&amp;lt;TIMESTAMP&amp;gt;|&amp;lt;RANDOM&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> "Firefox|255.255.255.255|1395758143|42341" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;USER_LIST:{u|&amp;lt;u.userAgent&amp;gt;|&amp;lt;u.ip&amp;gt;|&amp;lt;u.timestamp&amp;gt;|&amp;lt;u.random&amp;gt;}; separator=", "&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> "Firefox|255.255.255.255|1395758143|42341" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;DP_UUIDS.1&amp;gt; AND &amp;lt;DP_UUIDS.2&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> dpuuid1 AND dpuuid2 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> users:[&amp;lt;USER_LIST:{user|&amp;lt;user.dpUuids.1&amp;gt; AND &amp;lt;user.dpUuids.2&amp;gt;}; separator=", "&amp;gt;] </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> users:[dpuuid1 AND dpuuid2] </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> test_known_string=loremlipsum&amp;amp;segid=&amp;lt;TRAITALIAS_LIST; separator=","&amp;gt;&amp;amp;test_dpuuid_1000=&amp;lt;DP_UUIDS.1000&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> test_known_string=loremlipsum&amp;amp;segid=trait_1,trait_2&amp;amp;test_dpuuid_1000=dpuuid_1000 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> test_dpuuids=&amp;lt;DP_UUIDS.(DPID)&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> test_dpuuids=dpuuid2 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> "&amp;lt;PID_ALIAS&amp;gt;|&amp;lt;DP_UUID&amp;gt;|&amp;lt;TRAITALIAS_LIST; separator=","&amp;gt;|&amp;lt;REMOVED_TRAITALIAS_LIST; separator=","&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> pid_alias|dp_uuid|trait_1,trait_2|trait_3,trait_4 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <codeblock>
       {"Users":&nbsp;[&lt;USER_LIST:{user|&lt;OPEN_BRACKET&gt; 
      &nbsp;&nbsp;&nbsp;"AAM_UUID":&nbsp;"&lt;user.aamUuid&gt;", 
      &nbsp;&nbsp;&nbsp;"DataPartner_UUID":&nbsp;"&lt;user.dpUuid&gt;", 
      &nbsp;&nbsp;&nbsp;"Segments":&nbsp;[&lt;user.segments:{seg|&lt;OPEN_BRACKET&gt;"Segment":&nbsp;"&lt;seg.traitAlias&gt;"&lt;CLOSE_BRACKET&gt;};&nbsp;separator=","&gt;] 
      &nbsp;&nbsp;&nbsp;"Removed_Segments":&nbsp;[&lt;user.removedSegments:{rseg|&lt;OPEN_BRACKET&gt;"Segment":&nbsp;"&lt;rseg.traitAlias&gt;"&lt;CLOSE_BRACKET&gt;};&nbsp;separator=","&gt;] 
      &nbsp;&nbsp;&nbsp;&lt;CLOSE_BRACKET&gt;};&nbsp;separator=","&gt;]} 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> 
     <codeblock>
       {&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;"Users":[&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"AAM_UUID":"uuid1", 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"DataPartner_UUID":"dpuuid1", 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segments":[&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segment":"alias1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}, 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segment":"alias2" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;], 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Removed_Segments":[&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segment":"alias3" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}, 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segment":"alias4" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;] 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} 
      &nbsp;&nbsp;&nbsp;] 
      } 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <codeblock>
       {"Users":&nbsp;[&lt;USER_LIST:{user|&lt;OPEN_BRACKET&gt; 
      &nbsp;&nbsp;&nbsp;"AAM_UUID":&nbsp;"&lt;user.aamUuid&gt;", 
      &nbsp;&nbsp;&nbsp;"DataPartner_UUID":&nbsp;"&lt;user.dpUuid&gt;", 
      &nbsp;&nbsp;&nbsp;"Segments":&nbsp;[&lt;user.segments:{seg|&lt;OPEN_BRACKET&gt;"Segment":&nbsp;"&lt;seg.traitAlias&gt;","Status":&nbsp;"&lt;seg.status&gt;"&lt;CLOSE_BRACKET&gt;};&nbsp;separator=","&gt;] 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;CLOSE_BRACKET&gt;};&nbsp;separator=","&gt;]} 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> 
     <codeblock>
       {&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;"Users":[&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"AAM_UUID":"uuid1", 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"DataPartner_UUID":"dpuuid1", 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segments":[&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segment":"alias1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Status":"1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}, 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Segment":"alias2" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Status":"0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;] 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} 
      &nbsp;&nbsp;&nbsp;] 
      } 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;PID_ALIAS&amp;gt;|&amp;lt;DP_UUID&amp;gt;|&amp;lt;SEGMENTS:{seg|&amp;lt;seg.traitAlias&amp;gt;}; separator=\",\"&amp;gt;|&amp;lt;REMOVED_SEGMENTS:{seg|&amp;lt;seg.traitAlias&amp;gt;}; separator=\",\"&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> pid_alias|dp_uuid|trait_1,trait_2|trait_3,trait_4 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &amp;lt;if(user.segments &amp;amp;&amp;amp; user.removedSegments)&amp;gt;&amp;lt;COMMA&amp;gt;&amp;lt;endif&amp;gt; </span> </p> </td> 
   <td colname="col2"> <p>Prints a comma if the fields <span class="codeph"> segments </span> and <span class="codeph"> removedSegments </span> are not empty. This conditional can be used for POST requests when concatenating lists for segments and removed segments. </p> </td> 
  </tr> 
 </tbody> 
</table>

