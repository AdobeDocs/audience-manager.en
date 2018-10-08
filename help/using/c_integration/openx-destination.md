---
description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX as an Audience Manager Destination
uuid: abe44185-228d-4f6a-855e-d22b04458a2b
index: y
internal: n
snippet: y
translate: y
---

# OpenX as an Audience Manager Destination

Set up OpenX as a destination and send Audience Manager segment data to that platform.

## OpenX as an Audience Manager Destination {#topic_8CCCC636615B441E8899AB98745808C7}

Set up OpenX as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>For onsite ad server targeting only.

## OpenX Destination Requirements {#concept_0C2345ECE98F4AB3957502AD1C888555}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to OpenX.

<!-- aam-openx-requirements.xml -->

Review the following before setting up OpenX as an Audience Manager destination:

* **DIL:** Data Integration Library code should be deployed on your site. DIL helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data. 
* **get_aamCookie Function:** Code that captures the Audience Manager user ID and cookie data. Place [this code](../c_features/destinations/get-aam-cookie-code.md#reference_0102FABCC96547DE81DFCA0600BBEFD3) on the top of the page or inside the `<head>` codeblock. 

* **Send Delivery Logs to Audience Manager:** If you want a segment delivery report (optional), provide Audience Manager with a daily log that contains impression-level delivery data. The data can be in a raw format, but each record must contain the Audience Manager UUID. Audience Manager can pick up or receive these via FTP.

** Key-Value Data: Format Requirements**

Audience Manager sends data in the form of key-value pairs. Create key-value pairs according to the following specifications:

* Preface keys with `c.` (e.g., `c.color` or `c.price`). 

* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`). 
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`). 
* Key names should not contain special characters like accent and punctuation marks or other symbols.

**Only Qualified Segments are Sent to OpenX**

The amount data passed in to OpenX depends on how many segments a particular user qualifies for. For example, say you set up 100 Audience Management segments. If a site visitor qualifies for five of them, then only those five segments get sent to OpenX (not all 100). 

## Create an OpenX Destination {#concept_4A93689DF98A42368CF11A97F7522E8A}

Create a cookie-based destination for OpenX in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, DSP, ad network, etc.) that you want to share data with. [!UICONTROL Destination Builder] provides the tools that let you create and manage these data delivery processes. Audience Manager destination features are located in *Audience Data > Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

**Step 1: Basic Information**

To complete the [!UICONTROL Basic Information] section:

1. Name the destination. 
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list. 

1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

**Step 2: Configuration Information**

To complete the [!UICONTROL Configuration] section:

1. **Cookie Name:** Provide a short, descriptive name for your cookie. 
1. **Cookie Domain: **Leave blank to set a cookie in the domain of the user's current page. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`. 

1. Choose a key option in the [!UICONTROL Data Format] section. 
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values). 
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

**Step 3: Segment Mappings**

To add a segment to a cookie destination:

1. **Find segments:** The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. To find a segment:

    * Option 1: Start typing a segment name in the search field. The field updates automatically based on the text. Click **[!UICONTROL Add]** once you find the segment you want to use. 
    * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Add Mappings:** In the mappings pop, enter the segment ID in the mappings field and click **[!UICONTROL Save]**. 

1. Click **[!UICONTROL Done]**.

## OpenX Setup {#concept_07C3C67B234E4BE585E4B2BBD32C2D2B}

Modify OpenX settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

To set up OpenX

* Install DIL code across your site. 
* Create OpenX as a cookie destination in Audience Manager. 
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. The `get_aamCookie` code is available [here](../c_features/destinations/get-aam-cookie-code.md#reference_0102FABCC96547DE81DFCA0600BBEFD3). 

* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the OpenX destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name. Your ad tag could look similar example below. 

* 

  ```
  <a href= "http://client.adserver.net/?" + get_aamCookie('test_cookie') + 
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Remember to include `xid=` . It holds the actual unique user ID (UUID) passed in during an ad call.

The fully formed ad call could look similar to this: 

```
http://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```

