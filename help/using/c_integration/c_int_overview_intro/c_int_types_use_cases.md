---
description: A use-case summary of Audience Manager data integration methods along with the advantages and disadvantages of each.
seo-description: A use-case summary of Audience Manager data integration methods along with the advantages and disadvantages of each.
seo-title: Integration Use Cases
solution: Audience Manager
title: Integration Use Cases
uuid: 8fb269b9-61a8-4bef-be3c-02063ad98b10
index: y
internal: n
snippet: y
translate: y
---

# Integration Use Cases

**Real-Time Server-to-Server Integrations** 

A real-time server-to-server data integration rapidly synchronizes user data between Audience Manager servers and another targeting system. In most cases, data exchange takes place within seconds or minutes, depending on the refresh rate of the targeting system. Note, however, the targeted system determines this refresh interval, not Audience Manager. Furthermore, the refresh rate can vary between different systems. A real-time, server-to-server integration is the preferred integration type for data exchanges. Audience Manager uses this method whenever targeting partners can support it. 


<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Advantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Lets you qualify users for segments without seeing them again on the page, in a video player, etc. </li> 
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduces the number of HTTP calls from the page. Fewer calls helps preserve the user experience. </li> 
    <li id="li_046BF4568B104F53A0E5372568C957CD">Helps with time sensitive targeting so you can take action on a qualified user quickly. </li> 
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Useful when moving to a DSP for offsite targeting. </li> 
   </ul></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> Disadvantages:</td>
  <td class="stentry"> Less useful for onsite targeting when you need to target the user on the same page, or the next page, based on qualifying a user for that segment.</td> 
 </tr> 
</table>



**Server-to-Server Batch Integrations** 

A server-to-server batch integration bundles data and sends it to other systems at set intervals rather than in near real time. Data transfer intervals start from 24 hours. Some data providers support this integration type only. However, we've seen a general trend away from batch integrations towards real-time integration methodologies. 


<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Advantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Lets you qualify users for segments without seeing them again on the page, in a video player, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Useful for targeting that is not time sensitive. </li> 
   </ul></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> Disadvantages:</td>
  <td class="stentry"> The synchronization interval can delay targeting against the most current data.</td> 
 </tr> 
</table>



**Real-time Calls** 

Real-time calls exchange data with Audience Manager immediately, as a user visits your site or takes action on the page. With this method, targeting systems get the most updated segment qualification data and can take that information into account during a content or ad delivery decision. Also, this process works with publisher ad servers where we update qualified segments to a first-party cookie that is read into an ad call as key-value pairs. Currently, Audience Manager uses real-time calls to integrate with Target, Adobe Auditude/Primetime, and other content management systems. 


|  Advantages: | Lets you target the next page, content area, or ad impression based the most recent segment qualification. |
|---|---|
|  Disadvantages: | Adds a call to Audience Manager from the page. |



**Pixels Syncs to Targeting Systems** 

Pixel synchronization maps segments to pixels on the page. The pixel fires and transmits data when a user qualifies for a particular segment. Pixel synchronization is a rudimentary and unreliable data transfer mechanism. Top tier data providers and systems rarely use it. 
<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Advantages: </p></td>
  <td class="stentry"> <p> Real-time data transfers. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Disadvantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Can add a lot of client-side calls from the page. </li> 
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Unreliable for data transmission. 5% to 20% loss is normal. </li> 
   </ul></td> 
 </tr> 
</table>


