---
description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Receive Data From the DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
---

# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. This section includes a response example and definitions for common data elements in a response.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md#concept_9F6C569C1E444002ADF2A43516A9F284).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>
https://<i>domain alias</i>.demdex.net/event?<i>key1</i>= <i>val1</i>,&<i>key2</i>= <i>val2</i>&d_dst=1&d_rtbd=json&d_cb=<i>callback</i>
</code></pre>

## Sample Response {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md#concept_9F6C569C1E444002ADF2A43516A9F284) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. Yours may be similar or more complex.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Response Parameters {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| Parameter | Description |
|--- |--- |
|`c`|A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination).|
|`cn`|The name or ID set in the cookie name field of a [cookie destination](../../../features/destinations/manage-destinations.md#create-cookie-destination).|
|`cv`|The values sent to the destination defined by the "cn":" destinaton name" parameter.|
|`dcs_region`|The [server-to-server DCS calls](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091).|
|`dests`|This object contains information for all URL destinations which are configured in the UI. This object’s list is dynamic based on the user’s actions.|
|`dmn`|This is the domain specified in the  Cookie Domain field for a cookie destination. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`.|
|`e`|The secure URL that has been set in a URL destination.|
|`stuff`|This object contains information for all  Cookie destinations. This object’s list is dynamic based on the user’s actions.|
|`tid`|Transaction ID, which is a unique 12-character ID used for debugging purposes. Each /event call to the  DCS receives a tid that you can reference in support enquiries for a better and faster response.|
|`ttl`|The cookie time-to-live value in days.|
|`u` and `uuid`|Unique User ID assigned by  Audience Manager. This is required if you're making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md#concept_57686178E4174EE1A952E0E51BC8A52C).|
|`y`|Destination type,  iFrame (`iframe`) or image (`img`).|

>[!MORE_LIKE_THIS]
>
>* [Key-Value Prefixes and Variables Supported by the DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5)
