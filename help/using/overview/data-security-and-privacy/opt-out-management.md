---
description: Adobe complies with all industry-wide standards with regard to opt-out management. Read on for complete information on the types of opt-out supported by Audience Manager.
seo-description: Adobe complies with all industry-wide standards with regard to opt-out management. Read on for complete information on the types of opt-out supported by Audience Manager.
seo-title: Opt-out Management
solution: Audience Manager
title: Opt-out Management
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
---

# Opt-out Management{#opt-out-management}

Adobe complies with all industry-wide standards with regard to opt-out management. Read on for complete information on the types of opt-out supported by Audience Manager.

## Global Opt-Out {#global-opt-out}

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
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8"> Audience Manager User ID </a>: </p> <p> <pre> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </pre> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
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

## Partner Level Opt-Out {#partner-opt-out}

The partner-level opt-out permits opting out from data collection by specific Audience Manager partners. The partner-level opt-out works with [Declared ID](../../features/declared-ids.md#concept_2CD1CC1558354F38B3DEDBE09AE8E869) calls, as described in the sections below. Following a partner-level opt-out:

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8)) linked to the [CRM ID](../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8) is opted out of data collection. 

* Audience Manager will cease all data collection, segmentation or activation going forward for the last device ID linked to the CRM ID. 
* No historical data is deleted.

<br/>

**Opt-out Calls**

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#section_B6DDE03D9255430A92730E29B889023A), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md#concept_C1E36C6BF4C0461F9D31687E275DC46A"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**Examples**

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. See [CID Replaces DPID and DPUUID](../../reference/cid.md#concept_E9DE716F22E8491AB27057DB92B79081). In the examples, *italics* indicates a variable placeholder.

**Opt-Outs With CID and CID_IC**

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#concept_22E2210AA6604B83B46F5E0CD5504A51).

| Opt-Out Using | Code Sample |
|--- |--- |
|A data provider ID and user ID.|`https://  domain name /demoptout.jpg?d_cid=123%01987...`|
|An integration code and user ID.|`https://  domain name /demoptout?d_cid_ic=456%01321...`|
|Multiple  d_cid  and  d_cid_ic  key-value pairs.|`https://  domain name /demoptout?d_cid=123%01987&d_cid_ic=456%01321...`|


