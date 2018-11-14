---
description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS as an Audience Manager Destination
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
index: y
internal: n
snippet: y
---

# OAS as an Audience Manager Destination{#oas-as-an-audience-manager-destination}

Set up Open Ad Server as a destination and send Audience Manager data to that platform.

## OAS as an Audience Manager Destination {#topic_97281B7C2B7E464E9B87B556148B6235}

Set up Open Ad Server as a destination and send Audience Manager data to that platform. 

## OAS Destination Requirements {#concept_B999EF0522C14FF7BB55A8465D29EE0C}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to OAS.

<!-- 

aam-oas-requirements.xml

 -->

This destination type requires the following:

* **DIL:** Data Integration Library code should be deployed on your inventory. DIL helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data. 
* **get_aamCookie Function:** Code that captures the Audience Manager user ID and cookie data. Place [this code](../c-features/destinations/get-aam-cookie-code.md#reference_0102FABCC96547DE81DFCA0600BBEFD3) on the top of the page or inside the `<head>` codeblock. 

* **Send Delivery Logs to Audience Manager:** If you want a segment delivery report (optional), provide Audience Manager with a daily log that contains impression-level delivery data. The data can be in a raw format, but each record must contain the Audience Manager UUID. Audience Manager can pick up or receive these via FTP.

**Cookie Format and Key-Value Data**

Audience Manager can send segment data to a browser cookie as follows:

* Single keys ( `x=1&x=2`). 
* Multiple keys ( `x=1&x=2&y=3&y=4`). 
* Serialized values ( `x=1,2,3`) 
* A standard value delimiter used to separate individual key-value pairs.

**Only Qualified Segments are Sent to OAS**

The amount data passed in to OAS depends on how many segments a particular user qualifies for. For example, say you set up 100 Audience Management segments. If a site visitor qualifies for five of them, then only those five segments get sent to OAS (not all 100). 

>[!MORE_LIKE_THIS]
>
>* [get_aamCookie Code](../c-features/destinations/get-aam-cookie-code.md#reference_0102FABCC96547DE81DFCA0600BBEFD3)
>* [Key-Value Pairs Explained](../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)

## Create an OAS Destination {#concept_340EB01FB985459799AAD322303C2A8C}

Create a cookie-based destination for OAS in Audience Manager.

<!-- 

aam-oas-destination-setup.xml

 -->

In Audience Manager, a *destination* is any other system (ad server, DSP, ad network, etc.) that you want to share data with. [!UICONTROL Destination Builder] provides the tools that let you create and manage these data delivery processes. Audience Manager destination features are located in *Audience Data > Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

**Step 1: Basic Information**

To complete the [!UICONTROL Basic Information] section:

1. Name the destination. 
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list. 

1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

**Step 2: Configuration Information**

To complete the [!UICONTROL Configuration] section:

1. **Cookie Name: **Provide a short, descriptive name for your cookie. 
1. **Cookie Domain: **Leave blank to set a cookie in the domain of the user's current page. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`. 

1. Choose a key option in the [!UICONTROL Data Format] section. 
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values). 
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

**Step 3: Segment Mappings**

To add a segment to a cookie destination:

1. **Find segments:** The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. To find a segment:

    * Option 1: Start typing a segment name in the search field. The field updates automatically based on the text. Click **[!UICONTROL Add]** once you find the segment you want to use. 
    * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Add Mappings: **In the mappings pop, enter the segment ID in the mappings field and click **[!UICONTROL Save]**. 

1. Click **[!UICONTROL Done]**.

## OAS Setup {#concept_B7ADD24B44B24BB18E7445475EFECB11}

Modify OAS settings to work with Audience Manager segment data.

<!-- 

aam-oas-code.xml

 -->

To set up OAS

* Install DIL code across your site. 
* Create OAS as a cookie destination in Audience Manager. 
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. The `get_aamCookie` code is available [here](../c-features/destinations/get-aam-cookie-code.md#reference_0102FABCC96547DE81DFCA0600BBEFD3). 

* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the OAS destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name. Your ad tag could look similar example below. 

* 

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Remember to include the `u=` variable. It holds the actual unique user ID (UUID) passed in during an ad call. 
