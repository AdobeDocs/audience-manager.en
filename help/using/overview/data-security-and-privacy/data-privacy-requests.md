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

This document provides an overview of the data privacy requests that you can send to Audience Manager through the [Privacy Service UI](https://gdprui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send data privacy requests in compliance with GDPR and CCPA.

Before reading this article, we recommend going through the [GDPR Glossary](../aam-gdpr/aam-gdpr-faq.md) and [CCPA Glossary], to better understand the terminology used here.

## Overview {#overview}

You can submit individual requests to access and delete customer data from Audience Manager, in two ways:

* Through the [Privacy Service UI](https://gdprui.cloud.adobe.io/). See the documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Through the  **[!DNL Privacy Service API]**. See the documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) and the API reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending data privacy requests, you can submit any Audience Manager identifiers (IDs), as described in the **[Audience Manager Identifiers](../../overview/data-security-and-privacy/data-privacy-requests.md#aam-ids)** section, along with their respective namespace IDs (data source IDs).

The [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) supports two types of requests: data access and data deletion requests.

## Data Access Requests {#access-data}

You can send data access requests through the [Privacy Service UI](https://gdprui.cloud.adobe.io/) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Whether you are using the [!DNL UI] or the [!DNL API] to send data access requests, you must upload a [!DNL JSON] file with the Audience Manager identifiers for which you are submitting the data access request.

To see what a valid [!DNL JSON] file looks like, you can [download a sample JSON](../aam-gdpr/assets/access_request.json).

We understand your commitment to honoring your data privacy customer requests within 30 days of reception. For that reason, we try to process your data access request as soon as possible.

<!-- 
**Example Response**

A sample access response could look like the one below. In this example, the Data Subject's ID is a cookie ID. They qualified for several traits and belong to a few segments. The cookie ID is linked to a mobile ID. The example also contains metadata for the phone they use.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

The table below contains descriptions for all the returned fields in the data access response, in the order that they appear above.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>The user ID for the data that follows. This is either an id you provided in the GDPR data access request, or an ID that is linked to one of the declared IDs you provided. The ID types are described in the <a href="../../overview/data-security-and-privacy/data-privacy-requests.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Also referred to as data source. See the <a href="../../overview/data-security-and-privacy/data-privacy-requests.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>The ID of the namespace/data source. See <a href="../../overview/data-security-and-privacy/data-privacy-requests.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Integration codes are friendly names for your data sources, and help you track your data sources easier than using data source IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name </code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">For first party data, this is the customer's own company name. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">For second party data, this is the name of the partner company. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>The type of ID for which you requested the GDPR data access. Accepted types are listed in the <a href="../../overview/data-security-and-privacy/data-privacy-requests.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Incomplete request </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>A more detailed description of the warning you received: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Device Data - Contains data from all users of this device </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Incomplete request - Retrieval of Audience Manager data was not completed. Some information may be missing. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>The traits and segments associated with this user ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Traits associated with the user ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>The name of the trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>The trait type. The possible values are: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>First party</i> for your own traits. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Second party</i> for traits that belong to your partners. Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Third party</i> for traits obtained from data partners, via the <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>A few words to help describe the trait's purpose or function. This is an optional field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source that this trait belongs to. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">For first party data, this is the customer's own company name. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">For second party data, this is the name of the partner company. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this trait. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segments </code> </p> </td> 
   <td colname="col2"> <p>Segments that this user belongs to. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>The name of the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>A few words to help describe this segment. This is an optional field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source that this segment belongs to. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">For first party data, this is the customer's own company name. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">For second party data, this is the name of the partner company. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this segment. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>Indicates whether the Data Subject is currently qualified for this segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>Additional ID that this ID has been linked to. Information is returned on: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">data provider name </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>All these fields are described in the first rows of this table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>The exact time that an ID sync event made the link between IDs. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Information about the device. This information includes the fields below. Note that not all fields are returned for all device types. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Hardware information </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Device manufacturer </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>The marketing name of the device </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>The device model </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>The name of the device's Operating System (OS) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>The version of the OS </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>The device vendor </p> </li> 
     </ul> </p> <p> <p>Note: We only return device metadata when you submit either one of: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">Mobile IDs </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager IDs </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud IDs </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Data Deletion Requests{#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://gdprui.cloud.adobe.io/) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and API reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Whether you are using the [!DNL UI] or the [!DNL API] to send data deletion requests, you must upload a [!DNL JSON] file with the Audience Manager identifiers for which you are submitting the request.

To see what a valid [!DNL JSON] file looks like, you can [download a sample JSON](../aam-gdpr/assets/access_request.json).

We understand your commitment to honoring your data privacy customer requests within 30 days of reception. For that reason, we try to process your data deletion request as soon as possible.

In response to data deletion requests, we delete traits and segments associated with the Audience Manager identifier included in the request. Additionally, the respective Audience Manager identifiers for the Data Subject will be permanently opted out of further data collection by Audience Manager and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or cookie IDs, in data privacy requests, Audience Manager will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

## Opt-out Requests {#opt-out-request}

Adobe complies with all industry-wide standards with regard to opt-out management. Read on for complete information on the types of opt-out supported by Audience Manager.

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
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
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

### Partner Level Opt-Out with Declared ID calls

The partner-level opt-out helps you opt out from data collection by specific Audience Manager partners. Following a partner-level opt-out with a declared ID call:

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* Audience Manager will cease all data collection, segmentation or activation going forward for the last device ID linked to the CRM ID.
* No historical data is deleted.

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. See [CID Replaces DPID and DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Opt-Outs With CID and CID_IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Opt-Out Using | Code Sample |
|--- |--- |
|A data provider ID and user ID.|`https://domain name/demoptout.jpg?d_cid=123%01987...`|
|An integration code and user ID.|`https://domain name/demoptout?d_cid_ic=456%01321...`|
|Multiple  d_cid  and  d_cid_ic  key-value pairs.|`https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...`|

&nbsp;

### Partner Level Opt-Out with Device ID calls

The partner-level opt-out helps you opt out from data collection by specific Audience Manager partners. You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opt-Out Using | Code Sample |
|--- |--- |
|An Audience Manager Unique User ID (`uuid`).|`http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123`|
|An Experience Cloud ID (`mid`)|`http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid`|

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Following a partner-level opt-out with a device ID call:

* The device ID is opted out of data collection. 
* Audience Manager will cease all data collection, segmentation or activation, for the partner, going forward for the device ID.
* No historical data is deleted.

### Data Correction Requests {#correction}

Given that Audience Manager is not the source of the data, there is a limited role for data correction in Audience Manager. The correction could mean that the Data Subject has requested to either be disqualified from an incorrect trait/segment or qualified to the desired trait/segment.

Audience Manager Customers can choose to capture the relevant signals/traits/segments against user profiles and send this information through offline data ingestion to Audience Manager. Please note that the user will continue to get qualified to the original trait and segments if they repeat their behavior.
