---
description: Creates a partner-specific DIL instance.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
---

# DIL create method{#dil-create}

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

| Name | Type | Description |
|--- |--- |--- |
|`containerNSID`|Integer|This property sets the container ID used by [!DNL Audience Manager] for ID syncs. You would set `containerNSID` if you have [!UICONTROL DIL] deployed across multiple sites. Each of these sites will have their own container ID and ID syncs. When you have only 1 site, the container ID is 0 by default and you don't need to set this properly. Contact your consultant to get a list of your sites and their container IDs.<br>In the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), the property `idSyncContainerID` corresponds to `containerNSID` in [!UICONTROL DIL]. Note the following if you're using [!UICONTROL DIL] and the ID service across multiple sites: <ul><li>For each site, set the same con tainer IDs on `containerNSID` and `idSyncContainerID`.</li><li>Both [!UICONTROL DIL] and the ID service will try to send ID syncs to our data collection iFrame. However, the iFrame ensures that [!UICONTROL DIL] won't fire an ID sync. This prevents duplication.</li><li> Only [!UICONTROL DIL] sends data to a [URL destination](../../features/destinations/destinations.md#concept_88240D03005244DA91182932E9927003).</li></ul><br>See also, [idSyncContainerID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html).|
|`declaredId`|Object|`delcaredId` is used to pass in either the:<ul><li>`dpid`: Data partner ID assigned to you by [!DNL Audience Manager].</li><li>`dpuuid`: Your unique ID for a user.</li></ul><br>**Important**:  Only use un-encoded values for your IDs. Encoding will create double-encoded identifiers. <br>  **Note**: If you use the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), set customer IDs with the `setCustomerIDs` method instead of [!UICONTROL DIL]. See [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html).|
|`delayAllUntilWindowLoad`|Boolean|If true, defers all requests (IFRAME, event calls, ID sync, and destinationing) from executing until the `Page Load` event fires. Default is `false`.|
|`disableDeclaredUUIDCookie`|Boolean|False by default, which means [!DNL Audience Manager] sets a cookie in the partner's domain (sets a first party cookie).|
|`disableDestination`<br>`PublishingIframe`|Boolean|**Important**:  This element has been deprecated with [!UICONTROL DIL] version 8.0 (released August 2018). Use the `visitor.disableIdSyncs` [function](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html) in the Experience Cloud ID Service instead. <br>  If `true`, will not attach the destination publishing IFRAME to the DOM or fire destinations. Default is `false`.|
|`disableIDSyncs`|Boolean|**Important**:  This element has been deprecated with [!UICONTROL DIL] version 8.0 (released August 2018). Use the `visitor.disableIdSyncs` [function](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html) in the Experience Cloud ID Service instead. <br> Disables ID synchronization. You must disable ID syncs when using DIL v6.2+ and the Visitor ID Service. The `visitorService` function (see sample code below) takes care of this operation.|
|`enableErrorReporting`|Boolean|Set to `true` to enable error reporting for all [!UICONTROL DIL] instances on the page. Works with Boolean `true` only.|
|`iframeAkamaiHTTPS`|Boolean|**Important**:  This element has been deprecated with [!UICONTROL DIL] version 8.0 (released August 2018). Use the `visitor.idSyncSSLUseAkamai` [function](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html) in the Experience Cloud ID Service instead. <br>  Specifies if the destination publishing template should use Akamai for HTTPS connections. Enabled on a per-partner basis.|
|`mappings`|Object|Associates the value from one key-value pair to another. See  Map Key Values to Other Keys. Released with v2.4.|
|`namespace`|String|Required.<br>The `namespace` key-value pair contains your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. You need administrator permissions to view this dashboard. See the [Product Features and Functions FAQ](../../faq/faq-features.md#concept_9CC0A2A047DB434A8B697521047EA2D5) and [Administration - User Management and FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).|
|`partner`|String|Required. <br>Partner name as provided by [!DNL Audience Manager].|
|`removeFinishedScripts`<br>`AndCallbacks`|Boolean|Removes scripts and callbacks. Default is `False`. Applies to the current [!UICONTROL DIL] instance only. Released with v3.3.|
|`uuidCookie`|Object|Sets a cookie with the unique user ID returned from [!DNL Audience Manager]. See  uuidCookie Properties .|
|`visitorService`|Object|Required with [!UICONTROL DIL] 6.2 or greater. <br>DIL relies on the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service] to pass declared IDs into [!DNL Audience Manager]. See [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html) for more information.|


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
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
