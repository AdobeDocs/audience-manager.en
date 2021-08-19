---
description: Creates a partner-specific DIL instance.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
---
# DIL create method{#dil-create}

## DIL create {#dil-create-new}

Creates a partner-specific [!UICONTROL DIL] instance. 

**Function Signature:** `DIL.create: function (initConfig) {}`

**initConfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>The `visitorService` property is *always* required. Other properties listed here are optional, unless indicated otherwise.

`initConfig` accepts the following elements: 

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>This property sets the container ID used by <span class="keyword"> Audience Manager </span> for ID syncs. You would set <code> containerNSID </code> if you have <span class="wintitle"> DIL </span> deployed across multiple sites. Each of these sites will have their own container ID and ID syncs. When you have only 1 site, the container ID is 0 by default and you don't need to set this properly. Contact your consultant to get a list of your sites and their container IDs. </p> <p>In the <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, the property <code> idSyncContainerID </code> corresponds to <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Note the following if you're using <span class="wintitle"> DIL </span> <i>and</i> the ID service across multiple sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">For each site, set the same container IDs on <code> containerNSID </code> and <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Both <span class="wintitle"> DIL </span> and the ID service will try to send ID syncs to our data collection iFrame. However, the iFrame ensures that <span class="wintitle"> DIL </span> won't fire an ID sync. This prevents duplication. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Only <span class="wintitle"> DIL </span> sends data to a <a href="../../features/destinations/destinations.md"> URL destination </a>. </li> 
     </ul> </p> <p>See also, <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> is used to pass in either the: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Data partner ID assigned to you by <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Your unique ID for a user. </li> 
    </ul> <p> <p>Important:  Only use un-encoded values for your IDs. Encoding will create double-encoded identifiers. </p> </p> <p> <p>Note:  If you use the <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, set customer IDs with the <code> setCustomerIDs </code> method instead of <span class="wintitle"> DIL </span>. See <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> If true, defers all requests (IFRAME, event calls, ID sync, and destinationing) from executing until the <code> Page Load </code> event fires. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> False by default, which means <span class="keyword"> Audience Manager </span> sets a cookie in the partner's domain (sets a first party cookie). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> in the Adobe Experience Platform Identity Service instead. </p> </p> <p> If <code> true </code>, will not attach the destination publishing IFRAME to the DOM or fire destinations. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> in the Adobe Experience Platform Identity Service instead. </p> </p> <p>Disables ID synchronization. You must disable ID syncs when using DIL v6.2+ and the Visitor ID Service. The <code> visitorService </code> function (see sample code below) takes care of this operation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Set to <code> true </code> to enable error reporting for all <span class="wintitle"> DIL </span> instances on the page. Works with Boolean <code> true </code> only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> function </a> in the Adobe Experience Platform Identity Service instead. </p> </p> <p> Specifies if the destination publishing template should use Akamai for HTTPS connections. Enabled on a per-partner basis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Associates the value from one key-value pair to another. See <a href="../../dil/dil-use-cases.md#map-key-values"> Map Key Values to Other Keys </a>. Released with v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Required. </p> <p>The <code> namespace </code> key-value pair contains your <span class="keyword"> Experience Cloud </span> Organization ID. If you don't have this ID, you can find it in the <span class="wintitle"> Administration </span> section of the <span class="keyword"> Experience Cloud </span> dashboard. You need administrator permissions to view this dashboard. See the <a href="../../faq/faq-features.md"> Product Features and Functions FAQ </a> and <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - User Management and FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Required. </p> <p> Partner name as provided by <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Removes scripts and callbacks. Default is <code> False </code>. Applies to the current <span class="wintitle"> DIL </span> instance only. Released with v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Sets a cookie with the unique user ID returned from <span class="keyword"> Audience Manager </span>. See <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie Properties </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Required with <span class="wintitle"> DIL </span> 6.2 or greater. </p> <p> DIL relies on the <code> setCustomerIDs </code> function in the <span class="wintitle"> Adobe Experience Platform Identity Service </span> to pass declared IDs into <span class="keyword"> Audience Manager </span>. See <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Sample Code**

A sample [!UICONTROL DIL] call could look similar to the following:

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

A successful response returns the [!UICONTROL DIL] instance. An unsuccessful attempt returns an error object (not thrown) if your code is configured improperly or whenever an error is encountered. 

## uuidCookie Properties {#uuidcookie-props}

Defines the properties used by the `uuidCookie` variable. This variable is part of the `DIL.create` method. 

`uuidCookie` has the following properties:

<!-- 

r_dil_uuid_cookie.xml

 -->

|  Name  | Description  |
|---|---|
|  `name`  | The cookie name ( `aam_did` is default).  |
|  `days`  | Cookie lifetime (100 days is default).  |
|  `path`  | Cookie path, e.g., `'/test'` ( `/` is default).  |
|  `domain`  | The domain the cookie is set in, e.g., `'adobe.com'` ( `'.'+document.domain` is default).  |
|  `secure`  | Sets a flag to send data over an HTTPS connection only.  |

## visitorService Properties {#visitor-service-props}

Defines the properties used by the `visitorService` variable. This variable is part of the `DIL.create` method. 

`visitorService` has the following properties:

|  Name  | Type  | Description  |
|---|---|---|
|  `namespace`  | String  | Required. Represents The Experience Cloud Org ID. This is needed for Experience Cloud Core Service functionality. Same parameter used to instantiate the Visitor ID functionality.  |

**Code Sample:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
