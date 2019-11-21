---
description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: ID Synchronization for Outbound Data Transfers
uuid: f3849be8-1094-47db-9296-7482f020af18
---

# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.

<!-- c_id_sync_out.xml -->

## Purpose of ID Synchronization

ID synchronization is the first step in the outbound, asynchronous data transfer process. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. However, your data partner could identify this user with ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## URL Syntax

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL Parameters

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Unique user ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>Note:</b> Added only when the data provider initiates the call. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR applies).</p><p><b>Note:</b> <ul><li>The <code>gdpr</code> and <code>gdpr_consent</code> parameters are being gradually rolled out in ID sync URLs with activation partners. See Activation partners that support IAB TCF in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>).</p><p><b>Note:</b> This parameter can only be used together with <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Data Collection Components](../../reference/system-components/components-data-collection.md)
