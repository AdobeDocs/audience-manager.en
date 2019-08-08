---
description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Destination Builder

---

# Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] lets you create cookie-based or [!DNL URL] destinations. You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder] is located in **[!UICONTROL Audience Data > Destinations]**.

## Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consists of the following sections and settings:  

|[!UICONTROL Destination Builder] Section|Purpose|
|--- |--- |
|Basic Information|Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]).|
|Configuration|Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. You can send data as individual or serialized key-value pairs. For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Elements of a cookie destination such as cookie name, domain, size, expiration interval, data format, etc.</li></ul>|
|Segment Mappings|Lets you: <br/><ul><li>Search for, add, and manage segments associated with all destination types. </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul>|

## Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] and cookie-based destinations transmit data synchronously, as a user takes action on a page.
* Server-to-server data transmission is asynchronous and can occur long after a user has left the page. The delivery type you select depends on your business requirements and how a particular data partner wants to, or can, receive data.

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.