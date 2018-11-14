---
description: Audience Manager and the Experience Cloud ID service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-description: Audience Manager and the Experience Cloud ID service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Understanding Calls to the Demdex Domain
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
index: y
internal: n
snippet: y
---

# Understanding Calls to the Demdex Domain{#understanding-calls-to-the-demdex-domain}

Audience Manager and the Experience Cloud ID service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Call Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> demdex.net</span> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. It reflects <span class="keyword"> Audience Manager</span>'s original, pre-acquisition name (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> acquired <span class="keyword"> Demdex</span> in 2011 and re-branded the company as <span class="keyword"> Audience Manager</span>. It is difficult to change this domain because it is entwined deeply with <span class="keyword"> Audience Manager</span>, the <span class="wintitle"> ID service</span>, and our installed user base. See <a href="../c-am-overview-intro/aam-overview.md#concept_9848102C14C44A4D9BFC13A0CBE81F8E" format="dita" scope="local"> History and Background</a>. </p> <p>You may see other prefixes attached to legacy <span class="codeph"> demdex.net</span> calls (e.g., <span class="codeph"> dcs.demdex.net</span>, <span class="codeph"> fast.demdex.net</span>, etc.). Regardless of the prefix, a call to <span class="codeph"><span class="varname"> something</span>.demdex.net</span> is always a call to <span class="keyword"> Adobe</span> and not to some unknown or suspicious third-party domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dpm</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> is an abbreviation for <span class="wintitle"> Data Provider Match</span>. It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. This is the most common <span class="codeph"> demdex.net</span> call you'll see from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span>. </p> <p><span class="wintitle"> DPM</span> call basics: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: A <span class="wintitle"> DPM</span> call from <span class="keyword"> Audience Manager</span> sends data to the <span class="wintitle"> Data Collection Servers</span> and <span class="wintitle"> Profile Cache Servers</span>. See <a href="../reference/system-components/components-data-collection.md#concept_66CFFEBF5E8B41ED94082D562A93506E" format="dita" scope="local"> Data Collection Components</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID service</span> </b>: A <span class="wintitle"> DPM</span> call from the <span class="wintitle"> ID service</span> is a request for a visitor ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Experience Cloud ID Service Requests and Sets IDs</a>. </li> 
     </ul> </p> <p> <p>Note:  <span class="wintitle"> ID service</span> customers can change the <span class="wintitle"> DPM</span> prefix in the domain name. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server and audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)
