---
description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: Data Integration Methods
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
---

# Data Integration Methods {#data-integration-methods}

A high-level overview of how Audience Manager exchanges information with other data providers and systems.

## Supported Data Integration Methods: Real-Time and Server-to-Server {#section_79812B3411654D35AD5C401EA81072A4}

Choosing the right integration method depends on a combination of business requirements and the technical capabilities of your data partner. Audience Manager exchanges visitor information with other data providers by either of the following methods:

* **Real-Time:** Transfers data immediately as a user visits your site. This method is also known as a *`synchronous`* integration.
* **Batch (Server-to-Server):** Transfers data between servers on a set schedule after a visitor has left the page. This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#section_DE0B17CD8E7A494EA27D10C5394D6F14}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md#concept_98DD94EF9AA24422BA17B8D0760542DF) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. The taxonomy will contain all your traits organized in a logical hierarchy.

## Integration Use Cases {#concept_F75CB26BC3B64FBC9732F24563055466}

A use-case summary of Audience Manager data integration methods along with the advantages and disadvantages of each.

### Real-Time Server-to-Server Integrations

<!-- c_int_types_use_cases.xml -->

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

### Server-to-Server Batch Integrations

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

### Real-time Calls

Real-time calls exchange data with Audience Manager immediately, as a user visits your site or takes action on the page. With this method, targeting systems get the most updated segment qualification data and can take that information into account during a content or ad delivery decision. Also, this process works with publisher ad servers where we update qualified segments to a first-party cookie that is read into an ad call as key-value pairs. Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>Advantages: </p></td>
  <td> <p> Lets you target the next page, content area, or ad impression based the most recent segment qualification. </p></td> 
 </tr> 
 <tr>
  <td> <p>Disadvantages: </p></td>
  <td> <p>Adds a call to Audience Manager from the page.</p></td>
 </tr> 
</table>


### Pixels Syncs to Targeting Systems

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

## How to Choose a Data Delivery Method {#concept_4CCB9A4D0E0748DA8D6EA200ABBD20FC}

Describes technical and business reasons for sending data via synchronous (real-time) or asynchronous (server-to-server) methodologies.

<!-- c_int_delivery_choices.xml -->

### Selecting a Data Delivery Type

* **Technical Considerations:** Data delivery depends on the technical capabilities of the data partner. Audience Manager can send/receive data in real-time from the browser or by batch updates through offline, server-to-server communication processes.
* **Business Considerations:** The business reasons for selecting one delivery method or another depend on the technical capabilities of your destination partner and how you want to use this data. Typically, synchronous data transfers are useful when you need to take action on user data immediately. Asynchronous data transfers may be useful when immediate action is not required and when you have time to build deeper user profiles for later use.

## Real-Time Data Transfer Process {#concept_24E25472CC034AEBAEC8FC4F3421BB98}

A general overview of how Audience Manager performs a synchronous data exchange with a third-party vendor.

### Real-Time Data Transfer

<!-- c_int_overview_sync.xml -->

Real-time data transfers send and receive segment IDs as a user visits or takes action on your site. Typically, synchronous data transfers are useful when you need to qualify or segment users right away, as they navigate through your inventory.

### Real-Time Data Integration Steps

The real-time data integration process works as follows:

1. A user visits a customer's site that contains Audience Manager code.
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. The third party returns segment information about that user to Audience Manager.
1. Audience Manager ingests segment information and makes it available for targeting.

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#concept_EC5B2B3B5ED443F0B271400C08B263D3}

A general overview of how Audience Manager exchanges data synchronously (in real time) with a third-party vendor.

### Batch Data Integration

<!-- c_int_overview_async.xml -->

The batch (server-to-server) data integration process follows most of the steps outlined in the real-time data transfer process. However, instead of returning segment IDs immediately, user information is saved to our servers and synchronized with a third-party data provider at regular intervals. The asynchronous data transfer process is useful when:

* Immediate data transfers are not required.
* Collecting data to build a large pool of segmented users.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### Batch Data Integration Steps

1. A user visits a customer site.
1. Audience Manager and the third-party data provider assign the visitor a unique ID (usually with a cookie).
1. Audience Manager calls the third-party data provider to match visitor IDs.
1. A scheduled request, usually on a daily interval, exchanges visitor segment data between Audience Manager and your third-party data provider.

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md#concept_B4863966B22949C19F12A269C4BC2719).
