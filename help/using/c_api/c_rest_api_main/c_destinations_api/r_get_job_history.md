---
description: A GET method that returns outbound Server-to-Server (S2S) and bulk S2S destination job history information.
seo-description: A GET method that returns outbound Server-to-Server (S2S) and bulk S2S destination job history information.
seo-title: Return S2S and Bulk S2S Destination Job History
solution: Audience Manager
title: Return S2S and Bulk S2S Destination Job History
uuid: 48ee206c-273a-4e95-9e6d-352b7f31b195
index: y
internal: n
snippet: y
translate: y
---

# Return S2S and Bulk S2S Destination Job History


>**Request** 

>` GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&amp;endDate=1403034473000` 

>Required query parameters: ` startDate`=< *` epochtime`*> and *` endDate`*=< [!UICONTROL  epochtime]&gt;. 

>**Sample Response** 

>
>```
>[ 
>{ 
>      "pushID":34090, 
>      "orderID":655, 
>      "dataProviderID":269, 
>      "syncType":1, 
>      "fullPublish":false, 
>      "receivedRecords":1, 
>      "attemptedRecords":1, 
>      "successRecords":1, 
>      "startTime":1337292466000, 
>      "endTime":1337292466000, 
>      "dataFileName":"ftp_655_269_iter_1337229891903.sync", 
>      "success":true 
>   }, 
>   { 
>      "pushID":34104, 
>      "orderID":655, 
>      "dataProviderID":269, 
>      "syncType":1, 
>      "fullPublish":false, 
>      "receivedRecords":1, 
>      "attemptedRecords":1, 
>      "successRecords":1, 
>      "startTime":1337346397000, 
>      "endTime":1337346397000, 
>      "dataFileName":"ftp_655_269_iter_1337285714581.sync", 
>      "success":true 
>   }, 
>   { 
>      "pushID":34124, 
>      "orderID":655, 
>      "dataProviderID":269, 
>      "syncType":1, 
>      "fullPublish":false, 
>      "receivedRecords":1, 
>      "attemptedRecords":1, 
>      "successRecords":1, 
>      "startTime":1337396811000, 
>      "endTime":1337396812000, 
>      "dataFileName":"ftp_655_269_iter_1337338243600.sync", 
>      "success":true 
>   } 
>]
>```

