---
description: How declared IDs work, set up procedures, code examples, and variables.
keywords: id sync
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: Declared IDs
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
---

# Declared IDs {#declared-ids}

How declared IDs work, set up procedures, code examples, and variables.

## Declared ID Targeting {#declared-id-targeting}

Exchange and synchronize user IDs with Audience Manager from devices or browsers that do not use or accept persistent storage mechanisms, such as third-party cookies.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

Some browsers, and most mobile devices, do not accept third-party cookies. This makes it difficult to retain information about site visitors or assign persistent IDs. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. The following table describes the ID targeting/matching process:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Process </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Event Call</b> </td> 
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> gets <span class="wintitle"> declared IDs </span> from the <code> setVisitorID </code> function provided by the <span class="keyword"> Experience Cloud ID service </span> and passes that on to <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Match ID</b> </td> 
   <td colname="col2"> <p>Audience Manager attempts to match the client and visitor ID with a corresponding ID in our system. If a matching ID does not exist, Audience Manager creates a new ID and associates it with the client and visitor ID. </p> <p> <p>Note:  The most recent mapping is used if your ID maps to more than one Audience Manager ID. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Return ID</b> </td> 
   <td colname="col2"> <p>Audience Manager writes its synchronized ID to a first-party cookie (or other addressable storage space) in the client domain or application. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Subsequent Event Calls</b> </td>
   <td colname="col2"> <p>Additional event calls read the Audience Manager ID from the client's domain and send that to Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message "Encountered opt out tag", instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* The [!UICONTROL declared ID] opt-out is stored in the [!UICONTROL Profile Cache Server ([!UICONTROL PCS]) on a per-partner basis. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. See [CID Replaces DPID and DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opt-Outs With CID and CID_IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-Out Using </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A data provider ID and user ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>An integration code and user ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-Outs With DPID, DPUUID, and UUID (Deprecated)

These methods still work but are considered deprecated. This information is provided for legacy purposes and reference. Legacy opt-outs include:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-Out (Deprecated) </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> only </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Partner level opt-out </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. If there is no previously existing mapping, Audience Manager checks whether the request contains an AAM UUID in the cookie, and if it does, uses that for storing the opt-out. Otherwise, Audience Manager generates a new AAM UUID and stores the opt-out under it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> and explicit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> always takes precedence. If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Spaces have been added to make these easier to read.

In each key-value pair:

* The `=` symbol separates the key from its related values.
* The non-printing [!DNL ASCII] character `%01` separates the values.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contains a data provider ID and an associated unique user ID in a single key-value pair. <code> d_cid </code> replaces <code> d_dpid </code> and <code> d_dpuuid </code>, which are considered deprecated, but still supported. See <a href="../reference/cid.md"> CID Replaces DPID and DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contains an integration code and an associated unique user ID in a single key-value pair. <code> d_cid_ic </code> replaces <code> d_dpid </code> and <code> d_dpuuid </code>, which are deprecated, but still supported. See <a href="../reference/cid.md"> CID Replaces DPID and DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Event Calls {#sample-event-calls}

Given these key-value pairs and their required syntax, you would make event calls as shown below.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event Call Includes </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A data provider ID and user ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>An integration code and user ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In the `namespace` key-value pair, `MCORG` is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. You need administrator permissions to view this dashboard. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don't need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That's because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. However, we're referencing these variables here for historical and legacy purposes. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Data partner ID assigned by Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>The data provider's unique ID for the user. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` and `DPUUID`

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client's domain (first-party cookie) or other local storage.

Call this function when you're using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### Pass In IDs After DIL Instantiates

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Request/Response Examples {#request-response-examples}

The request sends a data provider and user ID to Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.

>[!MORELIKETHIS]
>
>* [CID Replaces DPID and DPUUID](../reference/cid.md)
