---
description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Real-Time Inbound Data Ingestion
uuid: ef7a70fd-8c6d-40ee-9b06-eb398b8967ff
index: y
internal: n
snippet: y
translate: y
---

# Real-Time Inbound Data Ingestion

Inbound data should be formatted as key-value pairs called signals. Typically, each signal is mapped to a segment created or managed through the user interface or API. 

## URL String Parameters and Syntax {#section_B804B3485D61445BB3908870EF7C60BF}

The URL for an inbound data transfer should contain the variables described below. Remember to [ create traits ](../../../../c_features/c_tb_overview/c_tb_main/c_trait_create/c_trait_create.md#concept_98DD94EF9AA24422BA17B8D0760542DF) and a [ folder structure ](../../../../c_features/c_tb_overview/c_tb_storage/t_tb_create_storage.md#task_5DC0C9CC9BAD4698A830EB04679C116E) in the [!DNL  Audience Manager] UI before setting up real-time data transfers. 
>[!NOTE]
>
>Replace italicized content with actual parameter values.



|  Parameter  | Description  |
|---|---|
|  ` *` <KEY>`*`  | A unique identifier in a key-value pair (e.g., gender, color, price).  |
|  ` *` <VAL>`*`  | A variable that belongs to the data set defined by the key (e.g., gender=male, color=green, price=100)  |

**URL Syntax** 

During a real-time inbound data ingestion process, a properly formatted URL string uses the following syntax: 
```
 
http://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC 
 

```

