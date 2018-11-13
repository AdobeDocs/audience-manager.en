---
description: Examples of some commonly used HTTP macro combinations.
seo-description: Examples of some commonly used HTTP macro combinations.
seo-title: HTTP Format Macro Examples
title: HTTP Format Macro Examples
uuid: a81a2e2a-de7e-4b6a-8771-fcfa0dc74570
index: y
internal: n
snippet: y
---

# HTTP Format Macro Examples{#http-format-macro-examples}

Examples of some commonly used HTTP macro combinations.

 See the [HTTP Format Macros](../formats/web-formats.md#reference_C392124A5F3F42E49F8AADDBA601ADFE) for a list of macros and their definitions.

<table id="table_D5FAC5D056ED49D79FA883197EF8F42E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro Examples </th> 
   <th colname="col2" class="entry"> Output Format </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;PID_ALIAS&gt;|&lt;DP_UUID&gt;|&lt;TRAITALIAS_LIST; separator=","&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> pid_alias|dp_uuid|trait_1,trait_2 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;PID_ALIAS&gt;|count:&lt;NUM_USERS&gt;|users:[&lt;USER_LIST:{user|&lt;user.aamUuid&gt;:&lt;user.dpUuid&gt;}; separator=", "&gt;] </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> "pid_alias|count:2|users:[uuid1:dpuuid1, uuid2:dpuuid2]" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;USER_AGENT&gt;|&lt;IP&gt;|&lt;TIMESTAMP&gt;|&lt;RANDOM&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> "Firefox|255.255.255.255|1395758143|42341" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;USER_LIST:{u|&lt;u.userAgent&gt;|&lt;u.ip&gt;|&lt;u.timestamp&gt;|&lt;u.random&gt;}; separator=", "&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> "Firefox|255.255.255.255|1395758143|42341" </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;DP_UUIDS.1&gt; AND &lt;DP_UUIDS.2&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> dpuuid1 AND dpuuid2 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> users:[&lt;USER_LIST:{user|&lt;user.dpUuids.1&gt; AND &lt;user.dpUuids.2&gt;}; separator=", "&gt;] </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> users:[dpuuid1 AND dpuuid2] </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> test_known_string=loremlipsum&amp;segid=&lt;TRAITALIAS_LIST; separator=","&gt;&amp;test_dpuuid_1000=&lt;DP_UUIDS.1000&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> test_known_string=loremlipsum&amp;segid=trait_1,trait_2&amp;test_dpuuid_1000=dpuuid_1000 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> test_dpuuids=&lt;DP_UUIDS.(DPID)&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> test_dpuuids=dpuuid2 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> "&lt;PID_ALIAS&gt;|&lt;DP_UUID&gt;|&lt;TRAITALIAS_LIST; separator=","&gt;|&lt;REMOVED_TRAITALIAS_LIST; separator=","&gt; </span> </p> </td> 
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
   <td colname="col1"> <p> <span class="codeph"> &lt;PID_ALIAS&gt;|&lt;DP_UUID&gt;|&lt;SEGMENTS:{seg|&lt;seg.traitAlias&gt;}; separator=\",\"&gt;|&lt;REMOVED_SEGMENTS:{seg|&lt;seg.traitAlias&gt;}; separator=\",\"&gt; </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> pid_alias|dp_uuid|trait_1,trait_2|trait_3,trait_4 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;if(user.segments &amp;&amp; user.removedSegments)&gt;&lt;COMMA&gt;&lt;endif&gt; </span> </p> </td> 
   <td colname="col2"> <p>Prints a comma if the fields <span class="codeph"> segments </span> and <span class="codeph"> removedSegments </span> are not empty. This conditional can be used for POST requests when concatenating lists for segments and removed segments. </p> </td> 
  </tr> 
 </tbody> 
</table>

