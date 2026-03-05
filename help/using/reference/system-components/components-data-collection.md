---
description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Data Collection Components
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
TQID: https://experienceleague.adobe.com/x5ryJCxXPXeT7cPV3oN5wIprkBlcechsRwu1qB5k6hQ
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
  - id: f15e67cf-b90e-44f4-ae50-f1fb9f866a27
    internal-label: Log files
  - id: f8c1669e-86ba-49c4-b622-9dfa07854df8
    internal-label: ID syncs
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
---
# Data Collection Components{#data-collection-components}

Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.

<!-- 

c_compcollect.xml

 -->

Audience Manager contains the following data-collection components:

* [Data Collection Servers (DCS) and Profile Cache Servers (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs) 
* [Data Integration Library (DIL)](../../reference/system-components/components-data-collection.md#dil) 
* [Inbound Server-to-Server](../../reference/system-components/components-data-collection.md#inbound-outbound-server) 
* [Log Files](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

The DCS and PCS work together and separately provide services related to trait realization, audience segmentation, and data storage.

**[!UICONTROL Data Collection Servers (DCS)] Function**

In [!DNL Audience Manager], the DCS:

* Receives and evaluates trait data from an event call. This includes information used for real-time segmentation and data passed in at scheduled intervals by server-to-server transfers. 
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md). 
* Creates and manages device IDs and authenticated profile IDs. This includes identifiers such as data provider IDs, user IDs, declared IDs, integration codes, etc. 
* Checks the PCS for additional traits a user has already realized prior to a real-time event call. This lets the DCS qualify users based on real-time data and historical data. 
* Writes log files and sends those to analytics systems for storage and processing.

**[!DNL DCS] Manages Demand Through [!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!DNL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] makes our system efficient because relevant data is cached in servers closest to the user. 

>[!IMPORTANT]
>
>The [!DNL DCS] only detects web traffic originating from devices that use IPv4.

In an event call, geographic location is captured in a key-value pair returned in a larger body of JSON data. This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!DNL DCS] indirectly through our data collection code. You can also work directly with the [!DNL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!DNL DCS]. [!UICONTROL PCS] data consists of device IDs, authenticated profile IDs, and their associated traits. When the [!DNL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]'s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. This behavior gives you a more complete and accurate picture of your users than from real-time qualifications alone.

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. The [!UICONTROL PCS] runs on Apache Cassandra.

**Purging inactive IDs from the [!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] calls 
* [!DNL /ibs] calls (ID syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

The [!UICONTROL PCS] flushes traits if they're inactive for 17-days. These traits aren't lost however. They're stored in Hadoop. If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**Other [!UICONTROL DCS/PCS] Processes: Privacy Opt-out**

These server systems handle privacy and user opt-out requests. User cookie information is not collected in the log file if a user has opted out of data collection. For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] is code you place on the page for data collection. See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

These are systems that receive data sent in by various server-to-server integrations with our clients. See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. These are sent to other database systems for processing, reporting, and storage. 

>[!MORELIKETHIS]
>
>* [Adobe Privacy Center](https://www.adobe.com/privacy.html)
