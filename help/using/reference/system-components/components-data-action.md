---
description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Data Action Components
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
---

# Data Action Components{#data-action-components}

Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] are files sent hourly to customers. These contain user IDs along with associated segment IDs, trait IDs, and other data. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

The [!UICONTROL SFTP/S3] publishers receive synchronized ID data from the [!UICONTROL Outbound Feed Converter]. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* Device ID/data provider IDs (DPUUID) 
* Qualified segment IDs 
* Trait IDs

[!DNL Audience Manager] customers do not have access to features that directly control the [!UICONTROL SFPT/S3 publishers]. Customers use this service indirectly when they create and send data to destinations. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. The [!UICONTROL IRIS] system is a namesake that reflects the characteristics of this figure from the ancient world. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] works with the same type of data as the [!UICONTROL SFTP/S3] system. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* Providing fast (within 30 seconds) synchronization for cookies and segments. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both. 
* Real-time data transfers. [!UICONTROL IRIS] is responsible for sending real-time segment qualification events to a partner or other destination. This data is JSON-formatted and sent via an HTTP `POST` request. 

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data. 

* Reliable infrastructure that works at scale and is fault tolerant. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**Segment Mapping Rules**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **New segment qualification**: when a device qualifies for a new segment, [!UICONTROL IRIS] sends all segments associated to that device to all of the destinations mapped to these segments. 

1. **New segment disqualification**: when a device no longer qualifies for a segment, [!UICONTROL IRIS] sends all segment qualifications and disqualifications associated to that device to all of the destinations mapped to these segments. 

1. **Destination mapping updates**: when a destination mapping is updated, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device. 

1. **Device graph updates**: when any device ID gets added or removed from the device graph used to evaluate a segment, [!UICONTROL IRIS] sends all segments associated to that device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

>[!IMPORTANT]
>
>If Audience Manager doesn't detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**Sample data file**

The following example contains real-time segment data from [!UICONTROL IRIS]. Keep in mind this is sample data only. Each customer may have different formatting requirements so the contents can vary.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md). 
