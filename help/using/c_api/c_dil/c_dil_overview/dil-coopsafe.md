---
description: An optional, Boolean configuration that determines if DIL sends (or does not send) data to the Adobe Experience Cloud Device Co-op.
seo-description: An optional, Boolean configuration that determines if DIL sends (or does not send) data to the Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: 2583d75d-4d27-4cea-836a-bf35eed64b9b
index: y
internal: n
snippet: y
translate: y
---

# isCoopSafe


>Contents: 

>
<ul class="simplelist"> 
 <li> <a href="../../../c_api/c_dil/c_dil_overview/dil-coopsafe.md#section_4883EDA6BEB8437182BCC82BB58FAE41" format="dita" scope="local"> Requirements </a> </li> 
 <li> <a href="../../../c_api/c_dil/c_dil_overview/dil-coopsafe.md#section_D18AF2B903F248E18AE8108AAF0A8EBB" format="dita" scope="local"> Use Cases </a> </li> 
 <li> <a href="../../../c_api/c_dil/c_dil_overview/dil-coopsafe.md#section_952F56724A2B4D349340E26FBAF33DDD" format="dita" scope="local"> Syntax and Code Sample </a> </li> 
 <li> <a href="../../../c_api/c_dil/c_dil_overview/dil-coopsafe.md#section_FCD441933506493FAEFAA6B51F194A17" format="dita" scope="local"> Event Call POST Parameters </a> </li> 
 <li> <a href="../../../c_api/c_dil/c_dil_overview/dil-coopsafe.md#section_9281C39C8B6249D7864100B5CBCA7DC6" format="dita" scope="local"> Post-Instantiation APIs </a> </li> 
</ul>



## Requirements {#section_4883EDA6BEB8437182BCC82BB58FAE41}

To use ` isCoopSafe` you must: 


* Use DIL v6.11 or higher.
* Participate in the [ Experience Cloud Device Co-op ](https://marketing.adobe.com/resources/help/en_US/mcdc/). Prospective co-op members should also review this documentation to determine if ` isCoopSafe` addresses possible concerns about how data is used to create the device graph.
* Work with your [!DNL  Adobe] consultant to set a whitelist or a blacklist flag on your Device Co-op account. There is no self-service path to enable these flags.


## Use Cases {#section_D18AF2B903F248E18AE8108AAF0A8EBB}

` isCoopSafe` helps resolve 2 use cases related to data collection by current or prospective members of the Device Co-op. These use cases relate to how site visitor data is passed on to the Device co-op to help build the device graph. The following table describes how ` isCoopSafe` works with these use cases to block or send data to the device graph 



<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Authenticated Visitors</b> </p> </td> 
   <td colname="col2"> <p>Add <span class="codeph"> isCoopSafe </span> to your DIL code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL on Third-Party Sites</b> </p> </td> 
   <td colname="col2"> <p>Add <span class="codeph"> isCoopSafe </span> to your DIL code for use on third-party sites where you: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">Cannot ensure that authenticated visitors have or have not accepted term-of-use agreements. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Need to control how that data is used by the Device Co-op to build the device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Syntax and Code Sample {#section_952F56724A2B4D349340E26FBAF33DDD}

**Syntax:** ` isCoopSafe: true | false` 

The Boolean options determine how customer data is or is not used by the Device Co-op. 

* ` isCoopSafe: true`: Visitor data collected by a mobile SDK or website *can* be used to help build the device graph.
* ` isCoopSafe: false`: Visitor data collected by a mobile SDK or website *cannot* be used to help build the device graph.
**Code Sample** 

Set this when DIL instantiates. 


```
jsvar dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```


## Event Call POST Parameters {#section_FCD441933506493FAEFAA6B51F194A17}

Depending on the flag you set ( ` true` or ` false`), DIL translates ` isCoopSafe` into these POST parameters and sends them to [!DNL  Adobe] in an event call: 


* ` d_coop_safe=1`
* ` d_coop_unsafe=1`


The POST parameters tell the [!DNL  Experience Cloud] Device Co-op if it can or cannot include user data in the device graph. The table below defines the relationship between the ` isCoopSafe` Boolean flags and the POST parameters passed in on an event call. If you don't use ` isCoopSafe`, neither of these are passed in an event call. 



<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuration Status </th> 
   <th colname="col2" class="entry"> POST Parameter </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> isCoopSafe: true </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> d_coop_safe=1 </span> </p> <p>The Device Co-op can use visitor data to help build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> isCoopSafe: false </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> d_coop_unsafe=1 </span> </p> <p>The Device Co-op cannot use visitor data to help build the device graph. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Post-Instantiation APIs {#section_9281C39C8B6249D7864100B5CBCA7DC6}

These APIs allow you to override the ` isCoopSafe` status. These are necessary because they let you change a visitor's post-instantiation/post-login status on a site or in a single page app where the page does not refresh. For example, you would need to call these APIs if a user authenticates to your site or app and later accepts a terms-of-use policy that allows the Device Co-op to use their data. 



<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dilInstance.api.setAsCoopSafe(); </span> </p> </td> 
   <td colname="col2"> <p>Sets POST parameter <span class="codeph"> d_coop_safe=1 </span> in all subsequent event calls. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dilInstance.api.setAsCoopUnsafe(); </span> </p> </td> 
   <td colname="col2"> <p>Sets POST parameter <span class="codeph"> d_coop_unsafe=1 </span> in all subsequent event calls. </p> </td> 
  </tr> 
 </tbody> 
</table>


<!-- Wiki page https://wiki.corp.adobe.com/x/RCfFTg -->

