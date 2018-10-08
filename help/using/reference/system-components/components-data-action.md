---
description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Data Action Components
uuid: 19073553-c1ed-4767-9df4-33b37729ded1
index: y
internal: n
snippet: y
translate: y
---

# Data Action Components

Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.

<!-- c_compact.xml -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

* [Custom Data Feeds (CDF)](../../reference/system-components/components-data-action.md#section_865029F74D96496D8AECAB69D95F4D6C) 
* [Data Collection Server (DCS)](../../reference/system-components/components-data-action.md#section_8C3E60777E6B47EABD4CACAB49B3F89B) 
* [SFTP/S3](../../reference/system-components/components-data-action.md#section_4E34FE0337534E5A84C6531330573085) 
* [IRIS](../../reference/system-components/components-data-action.md#section_1966DC17FD14419E943CEF04F13A005B) 
* [Profile Cache Server (PCS)](../../reference/system-components/components-data-action.md#section_5CB821F4E94947C5928D3154490EDD32)

## Customer Data Feeds (CDF) {#section_865029F74D96496D8AECAB69D95F4D6C}

[!UICONTROL CDF] are files sent hourly to customers. These contain user IDs along with associated segment IDs, trait IDs, and other data. For more information, see [Customer Data Feed Overview](../../c_features/cdf-files.md#concept_114B993EC5E246AE8CDD55E695B344FC).

## Data Collection Server (DCS) {#section_8C3E60777E6B47EABD4CACAB49B3F89B}

See [Data Collection Components](../../reference/system-components/components-data-collection.md#concept_66CFFEBF5E8B41ED94082D562A93506E).

## SFTP/S3 {#section_4E34FE0337534E5A84C6531330573085}

The [!UICONTROL SFTP/S3] publishers receive synchronized ID data from the [!UICONTROL Outbound Feed Converter]. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* Device ID/data provider IDs (DPUUID) 
* Qualified segment IDs 
* Trait IDs

[!DNL Audience Manager] customers do not have access to features that directly control the [!UICONTROL SFPT/S3 publishers]. Customers use this service indirectly when they create and send data to destinations. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#section_1966DC17FD14419E943CEF04F13A005B}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. The [!UICONTROL IRIS] system is a namesake that reflects the characteristics of this figure from the ancient world. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] works with the same type of data as the [!UICONTROL SFTP/S3] system. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* Providing fast (within 30 seconds) synchronization for cookies and segments. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both. 
* Real-time data transfers. [!UICONTROL IRIS] is responsible for sending real-time segment qualification events to a partner or other destination. This data is JSON-formatted and sent via an HTTP `POST` request. 

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data. 

* Reliable infrastructure that works at scale and is fault tolerant. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

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

## Profile Cache Server (PCS) {#section_5CB821F4E94947C5928D3154490EDD32}

See [Data Collection Components](../../reference/system-components/components-data-collection.md#concept_66CFFEBF5E8B41ED94082D562A93506E). 
