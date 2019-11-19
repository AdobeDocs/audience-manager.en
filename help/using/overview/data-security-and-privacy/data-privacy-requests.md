---
description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Data Privacy Requests
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
---

# Data Privacy Requests {#data-privacy-requests}

## Overview {#overview}

This document provides an overview of the data privacy and opt-out requests that you can send to Audience Manager through the [Privacy Service UI](https://gdprui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send data privacy requests in compliance with GDPR and CCPA.

Before reading this article, we recommend going through the [GDPR Glossary](../data-security-and-privacy/aam-gdpr-glossary.md) and [CCPA Glossary](aam-ccpa-glossary.md), to better understand the terminology used here.

You can submit individual requests to access and delete customer data from Audience Manager, in two ways:

* Through the [Privacy Service UI](https://gdprui.cloud.adobe.io/). See the documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Through the  **[!DNL Privacy Service API]**. See the documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) and the API reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending data privacy requests, you can submit any Audience Manager identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

The [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) supports two types of requests: data access and data deletion requests.

## Data Access Requests {#access-data}

You can send data access requests through the [Privacy Service UI](https://gdprui.cloud.adobe.io/) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

The [Privacy Service UI](https://gdprui.cloud.adobe.io/) allows you to create new job requests either by using the [!UICONTROL Request Builder] or by uploading a [!DNL JSON] file.

To see what a valid [!DNL JSON] file looks like, you can [download a sample JSON](../data-security-and-privacy/assets/access_request.json).

We understand your commitment to honoring your data privacy customer requests within 30 days of reception. For that reason, we try to process your data access request as soon as possible.

## Data Deletion Requests{#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://gdprui.cloud.adobe.io/) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and API reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

The [Privacy Service UI](https://gdprui.cloud.adobe.io/) allows you to create new job requests either by using the [!UICONTROL Request Builder] or by uploading a [!DNL JSON] file.

To see what a valid [!DNL JSON] file looks like, you can [download a sample JSON](../data-security-and-privacy/assets/access_request.json).

We understand your commitment to honoring your data privacy customer requests within 30 days of reception. For that reason, we try to process your data deletion request as soon as possible.

In response to data deletion requests, we delete traits and segments associated with the Audience Manager identifier included in the request. Additionally, the respective Audience Manager identifiers for the Data Subject will be permanently opted out of further data collection by Audience Manager and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or cookie IDs, in data privacy requests, Audience Manager will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

Audience Manager notifies activation partners about deletion requests by sending them unsegment information for Data Subjects requesting deletion of certain data. However, some activation partners:

1. Cannot support unsegment (or remove segment) requests from Adobe and/or
2. Are not able to receive updates from us with a frequency of less than 30 days. In those cases, Audience Manager Customers are not able to send delete requests to activation partners in an automated way through Audience Manager.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager.

Download our [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.

## Opt-out Requests {#opt-out-requests}

Adobe complies with all industry-wide standards with regard to opt-out management. Read on for complete information on the types of opt-out supported by Audience Manager.

While data access and deletion requests are handled through the [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), opt-out requests are currently supported through the DCS API. Read on to learn what the opt-out API calls should look like.

### Global Opt-out Requests

The global opt-out represents an opt-out across Audience Manager and other Adobe Experience Cloud solutions for all brands. The table below lists the methods used for global opt-out:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-Out For </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page </a> provides 1-click features that let your end users control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section </a> of the Privacy Choices page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direct API calls to Audience Manager </p> </td> 
   <td colname="col2"> <p>Your users can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile devices </p> </td> 
   <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Your end users can also opt out of global data collection by visiting the websites of our industry standards partners.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/); 
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Following the opt-out requests described above:

* Audience Manager will cease all data collection, segmentation or activation going forward.
* Historical data is removed from the user profile after 120 days.

### Partner Level Opt-out with Declared ID calls

The partner-level opt-out allows you to opt-out your users from data collection by specific Audience Manager partners. You can send partner-level opt-out requests for cross-device IDs, including CRM IDs and hashed email addresses.

Following a partner-level opt-out with a declared ID call:

* The [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection;
* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* Audience Manager will cease all data collection, segmentation or activation going forward for the CRM ID and the last device ID linked to the CRM ID;
* Audience Manager unsegments the opted-out CRM ID and last device ID from all segments;
* Destination partners receive the unsegment request for the CRM ID and last device ID. Unsegmentation works for both [real-time](data-privacy-requests.md#aam-partners-with-unsegmentation) and batch destinations.
* No historical data is deleted.

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. See [CID Replaces DPID and DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Opt-out With CID and CID_IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Opt-Out Using | Code Sample |
|--- |--- |
|A data provider ID and user ID.|`https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...`|
|An integration code and user ID.|`https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...`|
|Multiple  d_cid  and  d_cid_ic  key-value pairs.|`https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...`|

&nbsp;

### Partner Level Opt-Out with Device ID calls

The partner-level opt-out allows you to opt-out your users from data collection by specific Audience Manager partners. You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opt-Out Using | Code Sample |
|--- |--- |
|An Audience Manager Unique User ID (`uuid`).|`https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123`|
|An Experience Cloud ID (`mid`)|`https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid`|

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Following a partner-level opt-out with a device ID call:

* The device ID is opted out of data collection.
* Audience Manager will cease all data collection, segmentation or activation, for the partner, going forward for the device ID.
* Audience Manager unsegments the device ID from all segments;
* Destination partners receive the unsegment request for the device ID. Unsegmentation works for both [real-time](data-privacy-requests.md#aam-partners-with-unsegmentation) and batch destinations.
* No historical data is deleted.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate data privacy requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or 
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager.

Download our [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.

## Data Correction Requests {#correction}

Given that Audience Manager is not the source of the data, there is a limited role for data correction in Audience Manager. The correction could mean that the Data Subject has requested to either be disqualified from an incorrect trait/segment or qualified to the desired trait/segment.

Audience Manager Customers can choose to capture the relevant signals/traits/segments against user profiles and send this information through [offline data ingestion](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) to Audience Manager. Please note that the user will continue to get qualified to the original trait and segments if they repeat their behavior.
