---
description: Creates a partner-specific DIL instance.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
index: y
internal: n
snippet: y
---

# DIL create{#dil-create}

Creates a partner-specific DIL instance.

## DIL create {#reference_F87131F6C1CC4ECCA064B24B91710FD4}

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
   <td colname="col1"> <p> <span class="codeph"> containerNSID </span> </p> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>This property sets the container ID used by <span class="keyword"> Audience Manager </span> for ID syncs. You would set <span class="codeph"> containerNSID </span> if you have <span class="wintitle"> DIL </span> deployed across multiple sites. Each of these sites will have their own container ID and ID syncs. When you have only 1 site, the container ID is 0 by default and you don't need to set this properly. Contact your consultant to get a list of your sites and their container IDs. </p> <p>In the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a>, the property <span class="codeph"> idSyncContainerID </span> corresponds to <span class="codeph"> containerNSID </span> in <span class="wintitle"> DIL </span>. Note the following if you're using <span class="wintitle"> DIL </span> <i>and</i> the ID service across multiple sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">For each site, set the same container IDs on <span class="codeph"> containerNSID </span> and <span class="codeph"> idSyncContainerID </span>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Both <span class="wintitle"> DIL </span> and the ID service will try to send ID syncs to our data collection iFrame. However, the iFrame ensures that <span class="wintitle"> DIL </span> won't fire an ID sync. This prevents duplication. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Only <span class="wintitle"> DIL </span> sends data to a <a href="../../c-features/destinations/destinations.md#concept_88240D03005244DA91182932E9927003" format="dita" scope="local"> URL destination </a>. </li> 
     </ul> </p> <p>See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> declaredId </span> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Sends the <a href="../../c-features/declared-ids.md#reference_F697F0D53E56430D95EC0C408B767F80" format="dita" scope="local"> Declared ID variables </a> on every event call to <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <span class="codeph"> delcaredId </span> is used to pass in either the: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <span class="codeph"> dpid </span>: Data partner ID assigned to you by <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <span class="codeph"> dpuuid </span>: Your unique ID for a user. </li> 
    </ul> <p> <p>Important:  Only use un-encoded values for your IDs. Encoding will create double-encoded identifiers. </p> </p> <p> <p>Note:  If you use the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID Service </a>, set customer IDs with the <span class="codeph"> setCustomerIDs </span> method instead of <span class="wintitle"> DIL </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> delayAllUntilWindowLoad </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> If true, defers all requests (IFRAME, event calls, ID sync, and destinationing) from executing until the <span class="codeph"> Page Load </span> event fires. Default is <span class="codeph"> false </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> disableDeclaredUUIDCookie </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> False by default, which means <span class="keyword"> Audience Manager </span> sets a cookie in the partner's domain (sets a first party cookie). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> disableDestinationPublishingIframe </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <span class="codeph"> visitor.disableIdSyncs </span> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> If <span class="codeph"> true </span>, will not attach the destination publishing IFRAME to the DOM or fire destinations. Default is <span class="codeph"> false </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> disableIDSyncs </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <span class="codeph"> visitor.disableIdSyncs </span> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p>Disables ID synchronization. You must disable ID syncs when using DIL v6.2+ and the Visitor ID Service. The <span class="codeph"> visitorService </span> function (see sample code below) takes care of this operation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> enableErrorReporting </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Set to <span class="codeph"> true </span> to enable error reporting for all <span class="wintitle"> DIL </span> instances on the page. Works with Boolean <span class="codeph"> true </span> only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> iframeAkamaiHTTPS </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <span class="codeph"> visitor.idSyncSSLUseAkamai </span> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> Specifies if the destination publishing template should use Akamai for HTTPS connections. Enabled on a per-partner basis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mappings </span> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Associates the value from one key-value pair to another. See <a href="../../c-dil/dil-use-cases.md#concept_7FE441F32458474286DB9582DF791F1B" format="dita" scope="local"> Map Key Values to Other Keys </a>. Released with v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> namespace </span> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Required. </p> <p>The <span class="codeph"> namespace </span> key-value pair contains your <span class="keyword"> Experience Cloud </span> Organization ID. If you don't have this ID, you can find it in the <span class="wintitle"> Administration </span> section of the <span class="keyword"> Experience Cloud </span> dashboard. You need administrator permissions to view this dashboard. See the <a href="../../faq/faq-features.md#concept_9CC0A2A047DB434A8B697521047EA2D5" format="dita" scope="local"> Product Features and Functions FAQ </a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Administration - User Management and FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> partner </span> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Required. </p> <p> Partner name as provided by <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> removeFinishedScriptsAndCallbacks </span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Removes scripts and callbacks. Default is <span class="codeph"> False </span>. Applies to the current <span class="wintitle"> DIL </span> instance only. Released with v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> uuidCookie </span> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Sets a cookie with the unique user ID returned from <span class="keyword"> Audience Manager </span>. See <a href="../../c-dil/dil-class-overview/dil-create.md#reference_37603D122464476BBC1CCF8B047AF0C6" format="dita" scope="local"> uuidCookie Properties </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> visitorService </span> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Required with <span class="wintitle"> DIL </span> 6.2 or greater. </p> <p> DIL relies on the <span class="codeph"> setCustomerIDs </span> function in the <span class="wintitle"> Experience Cloud ID Service </span> to pass declared IDs into <span class="keyword"> Audience Manager </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a> for more information. </p> </td> 
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
  containerNSID:  
<i>3</i> 
}); 

```

A successful response returns the [!UICONTROL DIL] instance. An unsuccessful attempt returns an error object (not thrown) if your code is configured improperly or whenever an error is encountered. 

## uuidCookie Properties {#reference_37603D122464476BBC1CCF8B047AF0C6}

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

## visitorService Properties {#reference_963F24971BE340AFB077583DABF55C40}

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
        namespace: "INSERT-MCORG-ID-HERE" 
    } 
});
```

>[!MORE_LIKE_THIS]
>
>* [ID Service Implementation Guides](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html)

## uuidCookie Properties {#reference_F2E2F1F83B464935BE4942B46274FB77}

Defines the properties used by the `uuidCookie` variable. This variable is part of the `DIL.create` method. 

`uuidCookie` has the following properties:

<!-- 

r_dil_visitor_service.xml

 -->

|  Name  | Description  |
|---|---|
|  `name`  | The cookie name ( `aam_did` is default).  |
|  `days`  | Cookie lifetime (100 days is default).  |
|  `path`  | Cookie path, e.g., `'/test'` ( `/` is default).  |
|  `domain`  | The domain the cookie is set in, e.g., `'adobe.com'` ( `'.'+document.domain` is default).  |
|  `secure`  | Sets a flag to send data over an HTTPS connection only.  |

## visitorService Properties {#reference_89BBE552FE2445209A3E6080A9B8E080}

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
        namespace: "INSERT-MCORG-ID-HERE" 
    } 
});
```

>[!MORE_LIKE_THIS]
>
>* [ID Service Implementation Guides](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html)
