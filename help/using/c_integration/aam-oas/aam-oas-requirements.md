---
description: Standards for code placement, supported key-value formats, reports, and the type of segment data sent to OAS.
seo-description: Standards for code placement, supported key-value formats, reports, and the type of segment data sent to OAS.
seo-title: OAS Destination Requirements
solution: Audience Manager
title: OAS Destination Requirements
uuid: b59fc621-942b-4ff7-9d66-2b7d63ee2221
index: y
internal: n
snippet: y
translate: y
---

# OAS Destination Requirements

This destination type requires the following: 
* **DIL:** Data Integration Library code should be deployed on your inventory. DIL helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data.
* **get_aamCookie Function:** Code that captures the Audience Manager user ID and cookie data. Place [ this code ](../../c_features/c_destinations/r_aam_de_cookie.md#reference_0102FABCC96547DE81DFCA0600BBEFD3) on the top of the page or inside the ` <head>` codeblock.
* **Send Delivery Logs to Audience Manager:** If you want a segment delivery report (optional), provide Audience Manager with a daily log that contains impression-level delivery data. The data can be in a raw format, but each record must contain the Audience Manager UUID. Audience Manager can pick up or receive these via FTP.


**Cookie Format and Key-Value Data** 

Audience Manager can send segment data to a browser cookie as follows: 

* Single keys ( ` x=1&amp;x=2`).
* Multiple keys ( ` x=1&amp;x=2&amp;y=3&amp;y=4`).
* Serialized values ( ` x=1,2,3`)
* A standard value delimiter used to separate individual key-value pairs.
**Only Qualified Segments are Sent to OAS** 

The amount data passed in to OAS depends on how many segments a particular user qualifies for. For example, say you set up 100 Audience Management segments. If a site visitor qualifies for five of them, then only those five segments get sent to OAS (not all 100). 
>[!MORE_LIKE_THIS]
>
>* [ get_aamCookie Code ](r_aam_de_cookie.md#reference_0102FABCC96547DE81DFCA0600BBEFD3)
>* [ Key-Value Pairs Explained ](c_key_value_explained.md#concept_E4236E003076483AA939791FE2492B49)
