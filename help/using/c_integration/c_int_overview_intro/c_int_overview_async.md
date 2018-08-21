---
description: A general overview of how Audience Manager exchanges data synchronously (in real time) with a third-party vendor.
seo-description: A general overview of how Audience Manager exchanges data synchronously (in real time) with a third-party vendor.
seo-title: Batch Data Transfer Process
solution: Audience Manager
title: Batch Data Transfer Process
uuid: 493565a4-be98-420a-9cc3-bea332b06cc8
index: y
internal: n
snippet: y
translate: y
---

# Batch Data Transfer Process

**Batch Data Integration** 

The batch (server-to-server) data integration process follows most of the steps outlined in the real-time data transfer process. However, instead of returning segment IDs immediately, user information is saved to our servers and synchronized with a third-party data provider at regular intervals. The asynchronous data transfer process is useful when: 

* Immediate data transfers are not required.
* Collecting data to build a large pool of segmented users.
* You want to reduce data discrepancies and HTTP calls from the browser.
**Data Integration Steps** 

1. A user visits a customer site.
1. Audience Manager and the third-party data provider assign the visitor a unique ID (usually with a cookie).
1. Audience Manager calls the third-party data provider to match visitor IDs.
1. A scheduled request, usually on a daily interval, exchanges visitor segment data between Audience Manager and your third-party data provider.
![](assets/s2s_70.png) 

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server (S2S) file transfers, see [ Reporting and File Transfer Time-Frame Guidelines](../../c_reference/c_reporting_file_transfer_timeframe.md#concept_B4863966B22949C19F12A269C4BC2719). 
