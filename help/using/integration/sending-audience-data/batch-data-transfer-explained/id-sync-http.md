---
description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: ID Synchronization for Inbound Data Transfers
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
TQID: https://experienceleague.adobe.com/6pRhpoECN6jqncBykBth7wOKG8o592Ek1pS-dEzLMXk
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---
# ID Synchronization for Inbound Data Transfers {#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and [!DNL Audience Manager]. ID synchronization can begin after you send your data taxonomy to [!DNL Audience Manager].

ID synchronization is the first step in the inbound, asynchronous data transfer process. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. However, your data partner could identify this user with ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [ID Synchronization HTTP Request](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Declared ID Event](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID Synchronization From an Email Embedded Image](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

>[!NOTE]
>
>Replace italicized content with actual parameter values.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (Percent) Encoded representation of your Unique User ID. In addition to encoding reserved ASCII characters, any non-ASCII characters should be percent encoded based on the UTF-8 character encoding table. </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>Note:  Added only when the content provider initiates the call. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Add this parameter if you are using the <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR applies). </p> <p> <b>Note:</b> This parameter can only be used together with <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Add this parameter if you are using the <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>). </p> <p> <b>Note:</b> This parameter can only be used together with <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

The format for matching IDs via an email image is the same as shown above. Note, however, that images in an email must be enabled for this to work. This can affect ID synchronization via email because most mail systems disable images by default.

>[!MORELIKETHIS]
>
>* [Data Collection Components](../../../reference/system-components/components-data-collection.md)
