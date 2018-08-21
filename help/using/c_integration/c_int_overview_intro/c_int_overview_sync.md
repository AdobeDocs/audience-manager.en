---
description: A general overview of how Audience Manager performs a synchronous data exchange with a third-party vendor.
seo-description: A general overview of how Audience Manager performs a synchronous data exchange with a third-party vendor.
seo-title: Real-Time Data Transfer Process
solution: Audience Manager
title: Real-Time Data Transfer Process
uuid: 8e3dda91-c307-489c-ade4-227d7f68102d
index: y
internal: n
snippet: y
translate: y
---

# Real-Time Data Transfer Process

**Real-Time Data Transfer** 

Real-time data transfers send and receive segment IDs as a user visits or takes action on your site. Typically, synchronous data transfers are useful when you need to qualify or segment users right away, as they navigate through your inventory. 

** Data Integration Steps** 

The real-time data integration process works as follows: 
1. A user visits a customer's site that contains Audience Manager code.
1. Audience Manager loads an Iframe and makes a call to the Data Collection Server (DCS).
1. The DCS calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. The third party returns segment information about that user to Audience Manager.
1. Audience Manager ingests segment information and makes it available for targeting.


![](assets/rt_reduce70.png) 
