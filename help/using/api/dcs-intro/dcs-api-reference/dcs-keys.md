---
description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: Supported Attributes for DCS API Calls
uuid: 0b98ed11-314b-4500-afde-45a041112150
---

# Supported Attributes for [!UICONTROL DCS API] Calls {#supported-attributes-for-dcs-api-calls}

Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers ([!UICONTROL DCS]). This information can help you format your [!UICONTROL DCS] requests and understand the parameters returned by this system.

## Attribute Prefixes {#section_C40587830EFD4669AE9DAB5C6513CD9A}

The [!UICONTROL DCS] relies on specific prefixes added to the keys in key-value pairs to classify the type of data you're passing in.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key Prefix </th> 
   <th colname="col2" class="entry"> Reserved For </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> c_</span> </p> </td> 
   <td colname="col2"> <p>Customer-defined attributes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_</span> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> attributes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> h_</span> </p> </td> 
   <td colname="col2"> <p>HTTP header data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> p_</span> </p> </td> 
   <td colname="col2"> <p>Private, customer-defined attributes. </p> <p> The [!UICONTROL DCS] accepts your own, private data when the key has a <span class="codeph"> p_</span> prefix. Private data is used for trait evaluation, but it will not be logged or stored in our system. For example, lets say you have a trait defined as <span class="codeph"> customers = p_age&lt;25</span> and you pass in <span class="codeph"> p_age=23</span> in an event call. Given these conditions, the user who meets the age-based qualification criteria qualifies for the trait, but the key-value pair is dropped after <span class="keyword"> Audience Manager</span> receives the request and is not logged. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attributes {#section_B5B16D42E2004AF3ABCE25FFFEB0FF28}

All of these are optional, unless you want a response from the [!UICONTROL DCS]. If you want the [!UICONTROL DCS] to return a response, then `d_rtbd=json` is required.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_caller</span> </p> </td> 
   <td colname="col2"> <p>Used to identify the caller who is making the call to the <span class="wintitle"> DCS</span> API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_cb</span> </p> </td> 
   <td colname="col2"> <p>Specifies a JavaScript function you want to execute using the <span class="wintitle"> DCS</span> response as a function parameter of the callback function. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_cid</span> </p> </td> 
   <td colname="col2"> <p>Contains one or more pairs of data provider IDs (<span class="codeph"> DPID</span>) and data provider user IDs (<span class="codeph"> DPUUID</span>) assigned by <span class="keyword"> Audience Manager</span>. If you use multiple pairs of <span class="codeph"> DPID</span>s and <span class="codeph"> DPUUID</span>s, separate each pair with the non-printing character <span class="codeph"> %01</span>. For example: <span class="codeph"><span class="varname"> DPID</span>%01<span class="varname"> DPUUUID</span></span>. </p> <p><span class="codeph"> d_cid</span> replaces <span class="codeph"> d_dpid</span> and <span class="codeph"> d_dpuuid</span>, which are deprecated but still supported. See <a href="../../../reference/cid.md#concept_E9DE716F22E8491AB27057DB92B79081"> CID Replaces DPID and DPUUID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_cid_ic</span> </p> </td> 
   <td colname="col2"> <p>Contains an integration code and an associated unique user ID in a single key-value pair. </p> <p><span class="codeph"> d_cid_ic</span> replaces <span class="codeph"> d_dpid</span> and <span class="codeph"> d_dpuuid</span>, which are deprecated but still supported. See <a href="../../../reference/cid.md#concept_E9DE716F22E8491AB27057DB92B79081"> CID Replaces DPID and DPUUID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_coppa</span> </p> </td> 
   <td colname="col2"> <p>Disable usage of third party cookies in order to comply with child protection regulations. This parameter is dynamically set by the Adobe Experience Cloud ID service and depends on the <span class="codeph"> idSyncDisable3rdPartySyncing</span> configuration. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> COPPA Support in the Experience Cloud ID Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_cts=1</span> </p> <p><span class="codeph"> d_cts=2</span> </p> </td> 
   <td colname="col2"> <p>Optional. Enabled on customer request. Contact your Adobe Audience Manager consultant or Customer Care. </p> <p>Indicates that traits and segments should be returned inside the <span class="codeph"> JSON</span> response. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><span class="codeph"> d_cts=1</span> returns <a href="../../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8"> legacy segment IDs</a> for the segments. </p> </li> 
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><span class="codeph"> d_cts=2</span> returns segment IDs for the segments. </p> </li> 
     </ul> </p> <p>A sample response could look like the one below: </p> <p> 
     <codeblock class="syntax javascript">
      {
      
&nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      
&nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      
&nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      
&nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      
&nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      
&nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      
}
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_dpid</span> </p> </td> 
   <td colname="col2"> <p>Deprecated. See <span class="codeph"> d_cid</span> and <span class="codeph"> d_cid_ic</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_dpuuid</span> </p> </td> 
   <td colname="col2"> <p>Deprecated. See <span class="codeph"> d_cid</span> and <span class="codeph"> d_cid_ic</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_dst=1</span> </p> </td> 
   <td colname="col2"> <p>Returns URL destination data in the <span class="codeph"> JSON</span> response. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_dst_filter</span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> d_dst_filter</span> is a reserved attribute, used in the integration between Adobe Analytics and Audience Manager. </p> <p>We advise against creating traits that use reserved attributes. Adobe may change reserved attributes at any time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_jsonv=1|0</span> </p> </td> 
   <td colname="col2"> <p>Indicates the <span class="codeph"> JSON</span> version to use in the response. Normally, you should set this to <span class="codeph"> d_jsonv=1</span>. Setting <span class="codeph"> d_jsonv=0</span> disables ID syncs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_mid</span> </p> </td> 
   <td colname="col2"> <p>Specifies the Experience Cloud ID set and used by the <span class="keyword"> Experience Cloud</span> ID service. For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_nsid</span> </p> </td> 
   <td colname="col2"> <p>Name Space ID. Indicates which JavaScript container is used. Used by <span class="wintitle"> DIL</span> to for id-syncing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_ptfm </span> </p> </td> 
   <td colname="col2"> <p>Allows Audience Manager to distinguish mobile requests from desktop requests. Supported values include: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <span class="codeph"> ios</span> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <span class="codeph"> android</span> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <span class="codeph"> browser</span> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <span class="codeph"> all</span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_rs</span> </p> </td> 
   <td colname="col2"> <p>Deprecated. <span class="codeph"> d_rs</span> is a reserved attribute, used in the legacy integration between <span class="keyword"> Adobe Analytics</span> and <span class="keyword"> Audience Manager</span>. </p> <p>We advise against creating traits that use reserved attributes. Adobe may change reserved attributes at any time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_rtbd=json</span> </p> </td> 
   <td colname="col2"> <p>Required if you want a <span class="codeph"> JSON</span> response from the <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">If you omit this, the <span class="wintitle"> DCS</span> returns a pixel in the header. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">If you include this, the <span class="wintitle"> DCS</span> returns a <span class="codeph"> JSON</span> object in the body of the response. See the example below. Your response could be more complex. </li> 
     </ul> </p> <p> 
     <codeblock class="syntax javascript">
      {
      
&nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      
&nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      
&nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      
&nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      
}
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_sid</span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> SID</span> stands for <span class="term"> score ID</span>. This is a unique ID for a trait or a segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_tdpid</span> </p> </td> 
   <td colname="col2"> <p>Passes a data source for trait evaluation. Only traits from this data source are evaluated. </p> <p>For example, say you have: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Trait T1</b> with: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait rule: "<span class="codeph"> key1 == val1</span>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Data Source (<a href="../../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID integration code: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Trait T2</b> with: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait rule: "<span class="codeph"> key2 == val2</span>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Data Source (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID integration code: ic2 </li> 
     </ul> </p> <p>In a sample call, <span class="codeph">yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</span>, only trait T1 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_tdpid_ic</span> </p> </td> 
   <td colname="col2"> <p>The purpose is identical to the <span class="codeph"> d_tdpid</span> parameter described above. However, in this case, the data source is passed using the integration code. </p> <p>Keeping the traits described above, consider the sample call: </p> <p>For <span class="codeph">yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</span>, only trait T2 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> d_uuid</span> </p> </td> 
   <td colname="col2"> <p>Unique user ID. Identifies a visitor when this value is not available from a cookie. </p> </td> 
  </tr>
 </tbody>
</table>