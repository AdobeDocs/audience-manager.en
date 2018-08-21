---
description: In Audience Manager, a destination is any third-party system (ad server, DSP, ad network, etc.) that you want to share data with. Destination Builder helps you manage URL, cookie-based, or server-to-server destinations.
seo-description: In Audience Manager, a destination is any third-party system (ad server, DSP, ad network, etc.) that you want to share data with. Destination Builder helps you manage URL, cookie-based, or server-to-server destinations.
seo-title: Destination Publishing
solution: Audience Manager
title: Destination Publishing
uuid: fe5e892b-51b1-48dd-bec2-cd8092aacea8
index: y
internal: n
snippet: y
translate: y
---

# Destination Publishing

As a data management platform, it is important to standardize the data transfer mechanisms so they can be easily configured and managed by our systems. Audience Manager allows publishers to easily set up new targeting partners (destinations) in the interface. 

Audience Manager DIL code includes an asynchronous iframe that can be configured to perform ID syncs with third-party vendors, such as demand-side platforms and data providers. By default, no ID syncs are initiated from the iframe. Your Audience Manager consultant can enable them on your request. The purpose of an ID sync is to reconcile unique-visitor identifiers between Audience Manager and third-party vendors you might be working with. 

This asynchronous iframe is called from the DIL code or AudienceManagement module in [!DNL  Adobe Analytics], which typically loads at the bottom of the page after your site content is loaded. The asynchronous nature of the iframe allows the rest of the page to load while ID syncs are being made. When enabled, most ID syncs are configured to occur once per unique visitor per 14 days. 

## Supported Destination Types {#section_7C6466F301364E8884A5D2E0EF145AF4}

You can send information to a destination by passing it in through a URL string; by writing to a browser cookie; or through offline, server-to-server data transfers. URL and cookie-based destinations transmit data synchronously, as a user takes action on a page. Server-to-server data transmission is asynchronous and can occur long after a user has left the page. The delivery type you select depends on your business requirements and how a particular data partner wants to, or can, receive data. See [ Destinations ](../c_features/c_destinations/c_destinations.md#concept_5BDA346C376C4B719EA394108AB2735A) for more information. 

For each method, a publisher selects the appropriate data traits/segments to pass to each system. Publishers can pass the same segment to multiple platforms/channels simultaneously. 
