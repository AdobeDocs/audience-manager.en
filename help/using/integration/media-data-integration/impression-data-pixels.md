---
description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Capturing Campaign Impression Data via Pixel Calls
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
---

# Capturing Campaign Impression Data via Pixel Calls{#capturing-campaign-impression-data-via-pixel-calls}

One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.

This methodology is often referred to as "pixeling the creative." Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. The aggregated data provides a unified view of campaign performance, helps identify custom conversion paths, and helps customers improve the sequence of ad server events that lead to conversions.

## Event Call Syntax

>[!NOTE]
>
>The text styles (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) indicate code elements and options. See [Style Conventions for Code and Text Elements](../../reference/code-style-elements.md) for more information.

The event call collects impression and conversion data and sends it to the [!DNL Audience Manager] [data collection servers](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). This process relies on third-party ad servers that place the call in the creative to control what content gets inserted into the code. The third-party ad servers (for example, [!DNL DFA]) can place this code within each ad impression. Furthermore, an ad call does not use [!DNL JavaScript] or employ frame-busting techniques to access publisher data outside of the ad tag.

Event calls consist of key-value pairs that use the following syntax:

<pre>
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&
d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>
&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
</pre>

In the key-value pair, the value variable is an ID or macro inserted by the ad server. When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. This call does not return a response.

## Supported Key-Value Pairs {#supported-key-value-pairs}

Impression event calls accept data formed into key-value pairs. The following table lists and describes the keys used to hold these variables. Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>Numeric ad group ID from the ad server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>Data source ID or integration code for your advertiser. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Data source ID or integration code for your business unit. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-busting value. <span class="keyword"> Audience Manager </span> automatically sends cache-control headers that are honored by most browsers and proxies. If you want to perform additional cache busting, include this parameter in an event call, followed by a random string. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numeric campaign ID from the ad server. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). A fixed ID determines the mobile device type. The value, which is the user ID, can vary. Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. This parameter accepts the following keys: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifies an Android (GAID) device. For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifies an iOS (IDFA) device. For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numeric creative ID from the ad server. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifies an event call as an impression event. </p> <p>Required. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Numeric placement ID from the ad server. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Numeric site ID from the ad server. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Data source ID or integration code of the platform providing the metadata (e.g., DFA,  Atlas, GBM, Media Math, etc.). </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Please contact your Adobe Audience Manager consulting or account lead for the exact URL specific to the client domain.

>[!MORE_LIKE_THIS]
>
>* [Data and Metadata Files for Audience Optimization Reports](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
