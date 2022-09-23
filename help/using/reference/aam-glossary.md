---
description: Definitions and links to further reading.
seo-description: Definitions and links to further reading.
seo-title: Glossary
solution: Audience Manager
title: Glossary
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: Reference
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
---
# Glossary{#glossary}

Definitions and links to further reading.

## A-B {#a-b}

**Algorithmic Modeling**

Use [!UICONTROL Algorithmic Modeling] as a means of extending reach beyond the core of users you've identified. The feature helps you discover new, unique audiences through automated data analysis. Manage your [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

See [Understanding Algorithmic Models](../features/algorithmic-models/algo-models-overview.md).

**BAAAM**

[!UICONTROL Bulk Management Tools]. The [!UICONTROL Bulk Management Tools] in [!DNL Audience Manager] are a Microsoft Excel-based set of tools that let you create, modify or delete multiple objects at once with a single operation. You can work with data sources, derived signals, destinations, folders, segments, and traits. The feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs.

See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. A [!UICONTROL CDF] file represents a bulk download of data collected by [!DNL Audience Manager] and enables you to work with [!DNL Audience Manager] data outside of the limits imposed by our user interface. A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. This includes data like user IDs, trait IDs, segment IDs, and all the other parameters captured by an event call.

See [Customer Data Feeds](../features/cdf-files.md).

**CRM ID**

The CRM ID is the ID by which customers identify users in their own CRM system. Instead of CRM ID, we use the term DPUUID in Audience Manager.

See DPUUID in the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).



**Customer Addressable Audience**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents devices that:
* Have realized either a rule-based or an onboarded trait during the look-back window 
  **AND**
* Have an ID sync with the chosen destination regardless of the time of syncs.



**Customer Attributes**

See [Customer Attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.



**Customer Match Rate**

Customer Addressable Audience ÷ Customer Total Audience expressed as a %. See [Addressable Audience](/help/using/features/addressable-audiences.md).



**Customer Total Audience**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of devices that have realized either a rule-based trait on your properties or an onboarded trait from your offline files during the look-back window.



**demdex.net**

Demdex.net is a legacy domain controlled by [!DNL Adobe]. It reflects [!DNL Audience Manager]'s original, pre-acquisition name ( [!DNL Demdex]). [!DNL Adobe] acquired [!DNL Demdex] in 2011 and re-branded the company as [!DNL Audience Manager]. All HTTP calls to `demdex.net` domains are calls sent in to [!DNL Adobe].

See [Understanding Calls to the Demdex Domain](../reference/demdex-calls.md).



**DAID**

[!UICONTROL Device Advertising IDs] are unique device identifiers, used to identify a mobile device. These IDs are assigned by the device manufacturer, not by Adobe. We support iOS and Android device IDs in [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).



**Destination**

In [!DNL Audience Manager], a destination is any other system (ad server, DSP, ad network, etc.) that you want to share data with. The [!UICONTROL Destination Builder] in our UI provides the tools that let you create and manage these data delivery processes. [!DNL Audience Manager] destination features are located in **[!UICONTROL Audience Data > Destinations]**.



**DIL**

The [!UICONTROL Data Integration Library] is an API library used by [!DNL Audience Manager] to collect user interaction data. See [Data Integration Library (DIL) API](../dil/dil-overview.md).



**dpm**

[!UICONTROL Data Provider Match]. It tells internal [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the ID service is passing in customer data for synchronization or requesting an ID. See [Understanding Calls to the Demdex Domain](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Previously named the [!DNL Marketing Cloud] ID (MID or MCID). The [!DNL Experience Cloud] ID is central to the ID Service. It is a unique and persistent identifier for your site visitors. See Cookies and the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).



**Folder Trait**

Automatic grouping of traits inside your folder taxonomy. Each folder in your hierarchy automatically creates a trait which can be used to define segments.

See [Folder Traits: About](../features/traits/about-folder-traits.md).



**Frequency Capping**

A limit of a number of times that an advertiser wants to display a given creative to an end user. You can configure various frequency capping expressions in [!UICONTROL Segment Builder].

See [Recency and Frequency](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Google Advertising ID, the unique device ID that Google assigns to hardware devices running the Android operating system. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).



**GUID**

An acronym for Globally Unique Identifier. We don't use the term GUID in [!DNL Audience Manager]. In our case, the GUID is the [!DNL Audience Manager] UUID. 
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).  

## I-J {#i-j}

**IDFA**

Identifier for Advertisers, the unique device ID Apple assigns to its products. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).



**Inbound**

The process by which you can send audience data from other sources to [!DNL Audience Manager]. See [Sending Audience Data](/help/using/integration/sending-audience-data/send-audience-data.md).



**Integration Code**

When working with the [!DNL Audience Manager] UI or API, you have the option of adding an integration code when creating traits, segments, or data sources. Integration codes serve different purposes in those cases:

* [!UICONTROL Traits]: an integration code is a field for an ID, SKU, or other value used by your internal business processes. Optional. 
* [!UICONTROL Segments]: an integration code is a field for a user-defined ID or other company-specific information. Optional. 
* [!UICONTROL Data Sources]: integration codes are required when you want to create cross-device data sources, use the Adobe Experience Platform Identity Service, or work with [!UICONTROL Profile Merge Rules]. See [Create a Data Source](../features/manage-datasources.md#create-data-source) for more information.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

See [Algorithmic Modeling](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

See the [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. The [!UICONTROL PCS] is a large database, running on Apache Cassandra. It stores data received for active users from server-to-server transfers and the [!DNL DCS]. [!UICONTROL PCS] data consists of device IDs, authenticated profile IDs, and their associated traits.

See [Data Collection Components](../reference/system-components/components-data-collection.md).



**Profile Link**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).



**Profile Merge Rules**

[!UICONTROL Profile Merge Rules] let you control the type of data [!DNL Audience Manager] uses for segmentation.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realization**

The action by which a visitor on your site qualifies for a trait. You can use the [Visitor Profile Viewer](../features/visitor-profile-viewer.md) tool to obtain information on trait realization by a specific user.

## S-T {#s-t}

**Segment**

A segment (or an audience) is a set of users who share common attributes.

See [Segments: Purpose, Composition, and Rules](../features/segments/segments-purpose.md).



**Segment Addressable Audience**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents the number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via traits acquired in the [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).



**Segment Total Population**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of all the devices that were a member of your segment during the report look-back period.



**Segment Match Rate**

Segment Addressable Audience ÷ Total Segment Population expressed as a %. See [Addressable Audience](/help/using/features/addressable-audiences.md).



**Signal**

Signals are the smallest data units in [!DNL Audience Manager] and are expressed as key-value pairs.

See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).



**Trait**

A trait is a combination of one or more signals. See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).



**Trait Population**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live)**

TTL defines how many days a qualified visitor remains in a trait. TTL is set on traits and not on segments. Visitors fall out of a segment if they do not see a qualifying trait before the end of the TTL interval. Read more in [Segment and Trait Time-to-Live Explained](/help/using/features/traits/segment-ttl-explained.md).



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] Unique User ID. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).



**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

See the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) documentation.

## W-X-Y-Z {#w-z}
