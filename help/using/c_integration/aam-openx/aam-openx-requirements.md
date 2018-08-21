---
description: Standards for code placement, supported key-value formats, reports, and the type of segment data sent to OpenX.
seo-description: Standards for code placement, supported key-value formats, reports, and the type of segment data sent to OpenX.
seo-title: OpenX Destination Requirements
solution: Audience Manager
title: OpenX Destination Requirements
uuid: 3cdac236-30fd-4b62-801c-25d9960e503a
index: y
internal: n
snippet: y
translate: y
---

# OpenX Destination Requirements

Review the following before setting up OpenX as an Audience Manager destination: 
* **DIL:** Data Integration Library code should be deployed on your site. DIL helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data.
* **get_aamCookie Function:** Code that captures the Audience Manager user ID and cookie data. Place [ this code ](../../c_features/c_destinations/r_aam_de_cookie.md#reference_0102FABCC96547DE81DFCA0600BBEFD3) on the top of the page or inside the ` <head>` codeblock.
* **Send Delivery Logs to Audience Manager:** If you want a segment delivery report (optional), provide Audience Manager with a daily log that contains impression-level delivery data. The data can be in a raw format, but each record must contain the Audience Manager UUID. Audience Manager can pick up or receive these via FTP.


** Key-Value Data: Format Requirements** 

Audience Manager sends data in the form of key-value pairs. Create key-value pairs according to the following specifications: 
* Preface keys with ` c.` (e.g., ` c.color` or ` c.price`).
* Separate serialized values attached to a single key with a comma (e.g., ` c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., ` c.color=red &amp; c.price = 100 &amp; c.condition = new`).
* Key names should not contain special characters like accent and punctuation marks or other symbols.


**Only Qualified Segments are Sent to OpenX** 

The amount data passed in to OpenX depends on how many segments a particular user qualifies for. For example, say you set up 100 Audience Management segments. If a site visitor qualifies for five of them, then only those five segments get sent to OpenX (not all 100). 
