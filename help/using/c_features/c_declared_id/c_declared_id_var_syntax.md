---
description: Describes the variables and event call URLs that send IDs directly to Audience Manager.
seo-description: Describes the variables and event call URLs that send IDs directly to Audience Manager.
seo-title: URL Variables and Syntax for Declared IDs
solution: Audience Manager
title: URL Variables and Syntax for Declared IDs
uuid: 2721aa9d-e247-46c9-962b-997746aeb267
index: y
internal: n
snippet: y
translate: y
---

# URL Variables and Syntax for Declared IDs


## Variables and Syntax {#section_27D6F136B4094764BE71045354F50B3D}

The following table lists the key-value pairs that pass in your [!DNL  Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Spaces have been added to make these easier to read. 

In each key-value pair: 
* The = symbol separates the key from its related values.
* The non-printing ASCII character ` %01` separates the values.




<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">d_cid = <span class="varname"> data provider ID</span> %01 <span class="varname"> user ID</span></span> </p> </td> 
   <td colname="col2"> <p>Contains a data provider ID and an associated unique user ID in a single key-value pair. <span class="codeph"> d_cid</span> replaces <span class="codeph"> d_dpid</span> and <span class="codeph"> d_dpuuid</span>, which are considered deprecated, but still supported. See <a href="../../c_reference/cid.md#concept_E9DE716F22E8491AB27057DB92B79081" format="dita" scope="local"> CID Replaces DPID and DPUUID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">d_cid_ic = <span class="varname"> integration code</span> %01 <span class="varname"> user ID</span></span> </p> </td> 
   <td colname="col2"> <p>Contains an integration code and an associated unique user ID in a single key-value pair. <span class="codeph"> d_cid_ic</span> replaces <span class="codeph"> d_dpid</span> and <span class="codeph"> d_dpuuid</span>, which are deprecated, but still supported. See <a href="../../c_reference/cid.md#concept_E9DE716F22E8491AB27057DB92B79081" format="dita" scope="local"> CID Replaces DPID and DPUUID</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Sample Event Calls {#section_E7B2BD77EFA540CC968D981048900AA6}

Given these key-value pairs and their required syntax, you would make event calls as shown below. 



<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event Call Includes </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A data provider ID and user ID. </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://<span class="varname"> domain name</span>/event?d_cid=123%01987...</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>An integration code and user ID. </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://<span class="varname"> domain name</span>/event?d_cid_ic=456%01321...</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <span class="codeph"> d_cid</span> and <span class="codeph"> d_cid_ic</span> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://<span class="varname"> domain name</span>/event?d_cid=123%01987&amp;d_cid_ic=456%01321...</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ CID Replaces DPID and DPUUID ](cid.md#concept_E9DE716F22E8491AB27057DB92B79081)
