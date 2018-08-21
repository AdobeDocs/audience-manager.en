---
description: Describes the configuration variables used to pass declared IDs through DIL to Audience Manager.
seo-description: Describes the configuration variables used to pass declared IDs through DIL to Audience Manager.
seo-title: Declared ID Variables
solution: Audience Manager
title: Declared ID Variables
uuid: ff672d4c-34a1-449d-848f-c1336d911c1d
index: y
internal: n
snippet: y
translate: y
---

# Declared ID Variables



## DIL Uses the Visitor ID Service to Pass Declared IDs {#section_2BF6DF66A50747BAB77C1427DDCCC218}

When used with the [ Visitor ID Service ](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in a declared IDs with the deprecated ` dpid` and ` dpuuid` variables. Instead, the current versions of [!UICONTROL  DIL] rely on the ` visitorService` function to get the declared IDs from the ` setCustomerIDs` function in the [!UICONTROL  Visitor ID Service]. For more information, see [ Customer IDs and Authentication States ](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call ` visitorService` in ` DIL.create`as shown below. 


```
jsvar vDil = DIL.create({ 
  partner:"partner name", 
  visitorService:{ 
    namespace:"INSERT-MCORG-ID-HERE" 
  } 
});
```


In the ` namespace` key-value pair, ` MCORG` is your [!DNL  Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL  Administration] section of the [!DNL  Experience Cloud] dashboard. You need administrator permissions to view this dashboard. See [ Administration: Core Services ](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html). 

## Deprecated Functions {#section_5CC20964A1D342F7B0CBC3B6120FF78C}

With the latest versions of DIL (6.2+), you don't need to use these key-value pairs to pass in declared IDs. That's because DIL now relies on the ` visitorService` function shown in the code sample above. This function gets declared IDs from the [!UICONTROL  Visitor ID Service]. However, we're referencing these variables here for historical and legacy purposes. See the code below for an example of how to configure ` DIL.create` to get a declared ID from the [!UICONTROL  Visitor ID Service]. 
The following table describes the legacy variables used by the ` declaredId` object: 
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
   <td colname="col1"> <span class="codeph"> dpid </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Data partner ID assigned by Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> dpuuid </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>The data provider's unique ID for the user. </p> </td> 
  </tr> 
 </tbody> 
</table>

**dpid and dpuuid** 

Audience Manager compares and matches the combined ` dpid` and ` dpuuid` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the ` ` dpid`` ` /dpuuid` combination. Once Audience Manager matches or creates a user ID (the ` uuid`) it returns that ID in the JSON response to the cookie in the client's domain (first-party cookie) or other local storage. 

Call this function when you're using DIL v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets delcared IDs from the [!UICONTROL  Visitor ID Service]. 


```
jsDIL.create({ 
    partner : "partner name", 
    declaredId : { 
       dpuuid :  
<span class="varname"> <dpuuid> </span>, 
       dpid :  
<span class="varname"> <dpid> </span> 
    } 
 });
```



>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the ` d_dpuuid` and ` d_dpid` keys. 



**Pass In IDs After DIL Instantiates** 


>[!NOTE]
>
>If you make an API call with a different ` declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original ` DIL.create` ` declaredID` combination. 


```
jsDIL.getDil('partner name').api.signals({...}).declaredId({ 
  dpuuid :  
<span class="varname"> <dpuuid> </span> 
  dpid :  
<span class="varname"> <dpid> </span> 
}).submit();
```


## Request/Response Examples {#section_04668DDC7A83447C8B24F8D3C009ACB3}

The request sends a data provider and user ID to Audience Manager: 
```
http://my_domain.net/event?d_rtbd=json&amp;d_cb=myCallback&amp;key=val&amp;d_dpuuid=1234&amp;d_dpid=5678
```


The response returns the Audience Manager ID (e.g., uuid) which is written to a first-party cookie in the page domain. 
```
jsmyCallback({ 
... 
   "uuid":"abc123" 
})
```


## Do Not Target and Opt-Out Calls {#section_BAEA7C88783B4E7096A6B95F4F040652}

The declared ID process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the DCS returns an empty JSON object instead of the Audience Manager user ID. 
>[!MORE_LIKE_THIS]
>
>* [ Declared ID Targeting ](declared_id_about.md#concept_CB958007B9DA4251BA724B5607AD9FC3)
