---
description: Destination Builder lets you create cookie-based or URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-description: Destination Builder lets you create cookie-based or URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Destination Builder
uuid: 3d208190-ef0f-494a-aca3-3bd0d878f435
index: y
internal: n
snippet: y
translate: y
---

# Destination Builder


## Destination Builder Settings {#section_CD7B38643BA34A4CABE50F24072A9DB3}

[!UICONTROL  Destination Builder] consists of the following sections and settings: 

<table id="table_64B5929CFEC84A308BBFC9FFCBAF1358"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Destination Builder Section </th> 
   <th colname="col2" class="entry"> Purpose </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Basic Information</b> </td> 
   <td colname="col2"> Used to name the destination, describe it, and select destination type (URL or cookie), and platform (all, Android, browser, or iOS). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Configuration</b> </td> 
   <td colname="col2"> <p>Includes controls for: </p> 
    <ul id="ul_2E6AB51D5DEA44059CABDFA985E4C3D1"> 
     <li id="li_F8076EDA9D6243A4A4FF50BC3394FB3A">Passing in key-value data to URL destinations. You can send data as individual or serialized key-value pairs. For details see, <a href="../../c_features/c_destinations/c_dest_serialized.md#concept_02436A7C6C574C799F079EB731A63262" format="dita" scope="local"> Destination Serialization </a> and <a href="../../c_features/c_destinations/key-value-pairs.md#concept_4CAA6E54ECFE4291B8626BEBEE98088A" format="dita" scope="local"> Standard and Serial Key-Value Pairs </a>. </li> 
     <li id="li_4DE7A032B315450CAE791D1A0C56774C">Elements of a cookie destination such as cookie name, domain, size, expiration interval, data format, etc. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segment Mappings</b> </td> 
   <td colname="col2"> <p>Lets you: 
     <ul id="ul_98A6E9B5C74341ACA00D807B728A88B7"> 
      <li id="li_578629E9962F46EC921EA75A2057FE95">Search for, add, and manage segments associated with <i>all</i> destination types. </li> 
      <li id="li_37BB2BDD6B2D4E4EA07B494CAE452CBF">Set delivery priorities on individual segments (for cookie-based segments only). </li> 
     </ul></p> </td> 
  </tr> 
 </tbody> 
</table>


## Data Delivery Methods {#section_EB5C0D945F7B46F3B860D22F0998F550}

Send information to a destination by passing it in through a URL string, by writing to a browser cookie, or through offline server-to-server data transfers. 

* URL and cookie-based destinations transmit data synchronously, as a user takes action on a page.
* Server-to-server data transmission is asynchronous and can occur long after a user has left the page. The delivery type you select depends on your business requirements and how a particular data partner wants to, or can, receive data.
See [ How to Choose a Destination Type ](../../c_features/c_destinations/destination-delivery-methods.md#concept_88240D03005244DA91182932E9927003) for more information. 
>[!MORE_LIKE_THIS]
>
>* [ Create a Cookie Destination ](create-cookie-destination.md#concept_2462AA1321984293A92CB174C41B3496)
>* [ Create a URL Destination ](create-url-destination.md#concept_51842672DFA943EA982B363E74D42DF8)
