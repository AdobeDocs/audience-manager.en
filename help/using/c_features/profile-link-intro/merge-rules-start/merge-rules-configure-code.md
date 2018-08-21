---
description: Follow these instructions to set up the Visitor ID Service, DIL, and mobile SDK code to work with your merge rules.
seo-description: Follow these instructions to set up the Visitor ID Service, DIL, and mobile SDK code to work with your merge rules.
seo-title: Configure Merge Rule Code
solution: Audience Manager
title: Configure Merge Rule Code
uuid: 91fcfffe-fc4e-4279-bb7b-b6c3c8be83da
index: y
internal: n
snippet: y
translate: y
---

# Configure Merge Rule Code

**Prerequisites:** You must set up a [ cross-device data source ](../../../c_features/profile-link-intro/merge-rules-start/create-cross-device-datasource.md#concept_396828374D1B48C988655B2ED817F29B) and [ profile merge rules ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#concept_169938D1988447E1B60896908A49C78A)*before* completing these procedures. 

Contents: 

* [ For Visitor ID Service Customers ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#section_F88AEB30F2474EFBB477C007CA55E4AA)
* [ Legacy DIL ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#section_70398F3346F0444A821BD62FC86E3C67)
* [ Configure SDKs ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#section_202F3455E6264E97929E12A8F9894788)

## For Visitor ID Service Customers {#section_F88AEB30F2474EFBB477C007CA55E4AA}

The [!UICONTROL  Visitor ID Service] and the latest version of [ DIL ](../../../c_api/c_dil/c_dil.md#concept_6D73ED3DBA604EE49B66B5572AA6A32C) are recommended when working with [!UICONTROL  Profile Merge Rules]. However, you don't have to use the [!UICONTROL  Visitor ID Service] to work with this feature. If you're just using DIL, see the [ legacy DIL section ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#section_70398F3346F0444A821BD62FC86E3C67) below. 

**Configure the Set Customer ID Function** 

When working with the [!UICONTROL  Visitor ID Service], the ` setCustomerIDs` function passes declared IDs to [!DNL  Audience Manager]. To use a profile merge rule, you must modify ` setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you've created a cross-device data source with the integration code ` my_datasource_ic`. To pass in a declared ID, you would add the integration code to the visitor ID function as shown in the modified code sample below. 

<table id="table_97F466CE75C446A288908D659516195C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Generic code sample </th> 
   <th colname="col2" class="entry"> Modified code sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 
     <codeblock class="syntax javascript">
       visitor.setCustomerIDs({ 
      &nbsp;"userid":{ 
      &nbsp;&nbsp;&nbsp;&nbsp;"id":"12345", 
      &nbsp;&nbsp;&nbsp;&nbsp;"authState":Visitor.AuthState.AUTHENTICATED 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> 
     <codeblock class="syntax javascript">
       visitor.setCustomerIDs({ 
      &nbsp;"my_datasource_ic":{ 
      &nbsp;&nbsp;&nbsp;&nbsp;"id":"12345", 
      &nbsp;&nbsp;&nbsp;&nbsp;"authState":Visitor.AuthState.AUTHENTICATED 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

For more information, see [ Create a Cross-Device Data Source ](../../../c_features/profile-link-intro/merge-rules-start/create-cross-device-datasource.md#concept_396828374D1B48C988655B2ED817F29B) and [ Customer IDs and Authentication States ](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html). 

**Configure DIL.create function** 

The latest versions of DIL now automatically pick up the declared ID from the ` visitorService` function in ` DIL.create` (see [ Declared ID Variables ](../../../c_features/c_declared_id/r_dil_declared_id_vars.md#reference_F697F0D53E56430D95EC0C408B767F80)). Check your ` DIL.create` function to make sure this is set up properly as shown in the code sample below. 


```
jsvar vDil = DIL.create({ 
   partner:"parnter name", 
   visitorService:{ 
      namespace:" 
<span class="varname"> INSERT-MCORG-ID-HERE </span>" 
   } 
});
```


In the namespace key-value pair, the ` *` MCORG`*` variable is your Experience Cloud Organization ID. If you don't have this ID, you can find it in the Administration section of the Experience Cloud dashboard. You need administrator permissions to view this dashboard. See [ Administration: Core Services ](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html). 

**Configure SDKs** 

See the [ Configure SDKs ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#section_202F3455E6264E97929E12A8F9894788) section below. 

## Legacy DIL {#section_70398F3346F0444A821BD62FC86E3C67}

If you're not using [!DNL  Visitor ID Service] yet, you really ought to. But, we understand that moving to new code requires careful thought and testing. In these cases, check your ` DIL.create` function to make sure this is set up properly as shown in the code sample below. 


```
jsDIL.create({ 
   partner:"partner name", 
   declaredId:{ 
      dpuuid: 
<span class="varname"> dpuuid </span>, 
      dpid: 
<span class="varname"> dpid </span> 
   } 
});
```


For more information, see the legacy DIL section in [ Declared ID Variables ](../../../c_features/c_declared_id/r_dil_declared_id_vars.md#reference_F697F0D53E56430D95EC0C408B767F80). 

**Configure SDKs** 

See the [ Configure SDKs ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#section_202F3455E6264E97929E12A8F9894788) section below. 

## Configure SDKs {#section_202F3455E6264E97929E12A8F9894788}

Check the methods in your SDK code that let you pass declared IDs from Android and iOS mobile devices. The variable names for the Android and iOS code libraries are the same: 

* ` dpid`: The cross-device data source ID.
* ` dpuuid`: The declared ID (i.e., the user ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Device type </th> 
   <th colname="col2" class="entry"> Method </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Android </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> setDpidAndDpuuid </span> </p> <p> <b>Syntax:</b> </p> <p> <span class="syntax javascript codeph"> public static void setDpidAndDpuuid(String dpid, String dpuuid); </span> </p> <p> <b>Example:</b> </p> <p> <span class="syntax javascript codeph"> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> iOS </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> audienceSetDpid:dpuuid </span> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290" 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"]; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

See also, [ Audience Manager Methods for Android ](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [ Audience Manager Methods for iOS ](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html). 
