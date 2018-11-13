---
description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Pixel-based Data Transfers
uuid: 0d010ae6-b254-4e4a-8651-d2562d36a5f3
index: y
internal: n
snippet: y
---

# Pixel-based Data Transfers{#pixel-based-data-transfers}

Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.

<!-- 

c_rt_inbound_pixel_transfers.xml

 -->

To enable inbound data transfers, the vendor and client would:

1. Determine which traits you wish the vendor or partner to fire. 
1. Get the pixel for the trait. In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait. 

1. Provide the URL to the vendor or partner.

**Examples**

This basic event call sends trait ID 1234 to [!DNL Audience Manager]. 

```

https://something.demdex.net/event?d_sid=1234"

```

You can serialize trait IDs in an event call to help reduce HTTP traffic from the page. Append additional trait IDs to the URL string as shown in the following example: 

```

https://something.demdex.net/event?d_sid=1234,5678,9876,5432"

```

