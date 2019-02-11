---
description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Experience Cloud ID Service
solution: Audience Manager
title: Get User IDs and Regions Through the Experience Cloud ID Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
---

# Get User IDs and Regions Through the Experience Cloud ID Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make [!UICONTROL DCS] API calls.

## Get the User ID from the ID Service Cookie {#section_F28F94780FEC4918B37B62AC9A64AF23}

The [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/) assigns visitor and region IDs to users who come to your website. These IDs identify users across all the solutions in the [!DNL Experience Cloud] and they are required if you want to make [!UICONTROL DCS] calls.

* The [!UICONTROL user ID] is required to identify and associate data with a particular visitor.
* The [!UICONTROL region ID] is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. See [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091).

ID service customers can extract this information from the ID service cookie or by calling a function. The table below describes the tasks or steps you need to complete to get started.

Code in *italics* represents a variable placeholder.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Check your <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>You need a <span class="keyword"> Experience Cloud</span> account to use the ID service. If you have a <span class="keyword"> Experience Cloud</span> account, great! </p> <p> If you're not part of the <span class="keyword"> Experience Cloud</span>, then sign up. We'd love to have you and there's always room for more. For instructions on how to set up an account, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Core Services - Enabling Your Solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID service</span> consists of JavaScript code that gets put on each page you want to use for data collection. See the ID service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> implementation guides</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Read the <span class="keyword"> ID service</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID service</span> stores the user and region ID in the AMCV cookie. The full cookie name is <span class="codeph">AMCV_<span class="varname"> ###</span>@AdobeOrg</span>. The <span class="codeph"><span class="varname"> ###</span></span> elements are placeholders for your organization ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Parse the AMCV cookie for these key-value pairs: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <span class="codeph">mid=<span class="varname"> user ID</span></span>: This key-value pair holds the <span class="keyword"> Experience Cloud</span> user ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <span class="codeph">aamlh=<span class="varname"> region ID</span></span>: This key-value pair holds the region ID (sometimes called a <span class="term"> location hint</span>) which is associated with a regional server name. </li> 
     </ul> </p> <p>You can make calls to the <span class="wintitle"> DCS</span> once you have the user and region IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Retrieve the <span class="keyword"> Experience Cloud ID</span> with getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Optional)</i> This function returns the <span class="keyword"> Experience Cloud</span> visitor ID. It is designed for custom solutions and specific use cases. See <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#section_0D6CAAA7A2404EB59274CA35DCB5E65B"> Working With getMarketingCloudVisitorID</a> below and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> related ID service documentation</a>. </p> <p>You don't need to use this if you get the user and location IDs from the ID service cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Working With getMarketingCloudVisitorID {#section_0D6CAAA7A2404EB59274CA35DCB5E65B}

Another way to get the visitor ID is with the `getMarketingCloudVisitorID` function. When invoked, this function queries the [!DNL ID service] and returns an ID. `getMarketingCloudVisitorID` accepts the optional `callback` argument as shown:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback Usage and Purpose

`callback` is optional. This function works without it, but returns an ID only when a visitor has a [!DNL Experience Cloud] cookie in their browser. If the visitor cookie is missing, or a visitor doesn't have an ID, the function returns an empty `()` object. This can happen even after the page loads and the visitor receives a new ID. To avoid this, `callback` forces this function to check for a visitor ID after the page loads. Without `callback`, the visitor ID function won't return an ID even if it's written to the visitor's browser later.

## Next Steps {#section_66EF69EF07CB48D487DA5C7A510ABDA0}

Once you have the user and region ID, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md#concept_57686178E4174EE1A952E0E51BC8A52C).