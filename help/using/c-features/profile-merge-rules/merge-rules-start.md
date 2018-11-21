---
description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Getting Started with Profile Merge Rules
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
index: y
internal: n
snippet: y
---

# Getting Started with Profile Merge Rules{#getting-started-with-profile-merge-rules}

To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.

## Getting Started with Profile Merge Rules {#topic_2EB0F774DC5A4766ACB825A33B9F3B5B}

To create [!UICONTROL Profile Merge Rules] review and complete the steps in each of the procedures described in this section.

<!-- 

merge-rules-start.xml

 -->

## Create a Cross-Device Data Source {#concept_3B7696B3EC77416492D3B99EBD79EA44}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Administrator permissions are required to create or edit a cross-device data source.

<!-- 

create-cross-device-datasource.xml

 -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../c-features/datasources-list-and-settings.md#reference_A87B381067E04C26A426514AF3B64E64) for descriptions of these different controls.

## Data Source Details {#section_D359CAAE0BEA4527B3A04855486033DE}

To complete the Data Source Details section:

1. Name the data source. 
1. *(Optional)* Describe the data source. A concise description helps you define the role or purpose of the data source. 
1. Provide an integration code. An integration code is your own, unique ID for this data source. 
1. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**. 

1. In the **[!UICONTROL ID Definition]** list, select an option that defines the data source type. Options include:

    * **[!UICONTROL Person]**: An ID that defines a single person. This ID can be mapped to multiple [!DNL Audience Manager] IDs. 
    
    * **[!UICONTROL Household]**: An ID that defines a group of people. This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## Data Export Controls {#section_895821268F6F42E9A181B717DD6F1D04}

[Data Export Controls](../../c-features/data-export-controls.md#concept_155AAFBA7D804467B6F8279D26C9D05C) are optional classification rules you can apply to a data source and destination. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#section_928E1EB8EE7149A88F46ABD3B6FE5BAF}

[!UICONTROL Data Source Settings] section provides multiple options, but these 2 are important for creating a cross-device data source:

* **[!UICONTROL Use as Authenticated Profile]**: Selected by default, this setting lets you build a [!UICONTROL Profile Merge Rule] with your own, authenticated data. 

* **[!UICONTROL Use as a Device Graph]**: This control is available only to accounts listed as a data provider. Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. Work with your [!DNL Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL Data Source] should be shared with. Your consultant will provision your account and device graph sharing through an internal provisioning processes.

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../c-features/profile-merge-rules/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list. 

>[!MORE_LIKE_THIS]
>
>* [Create a Data Source](../../c-features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44)

## Create a Profile Merge Rule {#concept_55706E2521944DF1A5C7B0E19C7436D0}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. You can create up to 3 merge rules after setting up a cross-device data source. Administrator permissions are required to create, edit, or delete a rule. All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- 

create-profile-merge-rule.xml

 -->

**Prerequisites:** A cross-device data source is required to build a [!UICONTROL Profile Merge Rule]. See [Create a Data Source](../../c-features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../c-features/profile-merge-rules/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0) for descriptions of these different controls.

## Basic Information {#section_A57B424647D647CF9687E99F21C318D7}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule]. 
1. *(Optional)* Describe the [!UICONTROL Profile Merge Rule]. A concise description helps you define the role or purpose of your rule. 

1. *(Optional)* Select **[!UICONTROL Set as default]** if you want to make this the default [!UICONTROL Profile Merge Rule]. New segments are automatically associated with the default rule.

## Data Export Controls {#section_6B22BFF8BA724DC38852D3437A8C171E}

[Data Export Controls](../../c-features/data-export-controls.md#concept_155AAFBA7D804467B6F8279D26C9D05C) are optional classification rules you can apply to your [!UICONTROL Profile Merge Rule]. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#section_61EEF440AC384395B86C222EFA5EB9EF}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. Options include:

    * **[!UICONTROL No Authenticated Profile]** 
    * **[!UICONTROL Current Authenticated Profile]** 
    * **[!UICONTROL Last Authenticated Profile]**

1. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../c-features/profile-merge-rules/merge-rules-start.md#concept_396828374D1B48C988655B2ED817F29B) you have created previously. 

1. Select a **[!UICONTROL Device Option]**. Options include:

    * **[!UICONTROL No Device Profile]** 
    * **[!UICONTROL Current Device Profile]** 
    * **[!UICONTROL Profile Link Device Graph]** 
    * **[!UICONTROL Device Co-op]**

1. Click **[!UICONTROL Save]**.

## Next Steps {#section_0A2D9E025E9646B89BE2B7634BCE743F}

Review and complete the procedures described in [Configure Merge Rule Code](../../c-features/profile-merge-rules/merge-rules-start.md#concept_169938D1988447E1B60896908A49C78A). 

>[!MORE_LIKE_THIS]
>
>* [Profile Merge Rule Options Defined](../../c-features/profile-merge-rules/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0)

## Configure Merge Rule Code {#concept_169938D1988447E1B60896908A49C78A}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile SDK code to work with your merge rules.

<!-- 

merge-rules-configure-code.xml

 -->

**Prerequisites:** You must set up a [cross-device data source](../../c-features/profile-merge-rules/merge-rules-start.md#concept_396828374D1B48C988655B2ED817F29B) and [profile merge rules](../../c-features/profile-merge-rules/merge-rules-start.md#concept_169938D1988447E1B60896908A49C78A) *before* completing these procedures.

Contents:

* [For Experience Cloud ID Service Customers](../../c-features/profile-merge-rules/merge-rules-start.md#section_F88AEB30F2474EFBB477C007CA55E4AA) 
* [Legacy DIL](../../c-features/profile-merge-rules/merge-rules-start.md#section_70398F3346F0444A821BD62FC86E3C67) 
* [Configure SDKs](../../c-features/profile-merge-rules/merge-rules-start.md#section_202F3455E6264E97929E12A8F9894788)

## For Experience Cloud ID Service Customers {#section_F88AEB30F2474EFBB477C007CA55E4AA}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../c-dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don't have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you're just using [!UICONTROL DIL], see the [legacy DIL section](../../c-features/profile-merge-rules/merge-rules-start.md#section_70398F3346F0444A821BD62FC86E3C67) below.

**Configure the Set Customer ID Function**

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you've created a cross-device data source with the integration code `my_datasource_ic`. To pass in a declared ID, you would add the integration code to the visitor ID function as shown in the modified code sample below. 

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

For more information, see [Create a Cross-Device Data Source](../../c-features/profile-merge-rules/merge-rules-start.md#concept_396828374D1B48C988655B2ED817F29B) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

**Configure DIL.create function**

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../c-features/declared-ids.md#reference_F697F0D53E56430D95EC0C408B767F80)). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

```js
var vDil = DIL.create({ 
   partner:"partner name", 
   visitorService:{ 
      namespace:" 
<varname>
  INSERT-MCORG-ID-HERE 
</varname>" 
   } 
});
```

In the namespace key-value pair, the ` *`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. You need administrator permissions to view this dashboard. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

**Configure SDKs**

See the [Configure SDKs](../../c-features/profile-merge-rules/merge-rules-start.md#section_202F3455E6264E97929E12A8F9894788) section below.

## Legacy DIL {#section_70398F3346F0444A821BD62FC86E3C67}

If you're not using [!DNL Experience Cloud ID Service] yet, you really ought to. But, we understand that moving to new code requires careful thought and testing. In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

```js
DIL.create({ 
   partner:"partner name", 
   declaredId:{ 
      dpuuid: 
<varname>
  dpuuid 
</varname>, 
      dpid: 
<varname>
  dpid 
</varname> 
   } 
});
```

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../c-features/declared-ids.md#reference_F697F0D53E56430D95EC0C408B767F80).

**Configure SDKs**

See the [Configure SDKs](../../c-features/profile-merge-rules/merge-rules-start.md#section_202F3455E6264E97929E12A8F9894788) section below.

## Configure SDKs {#section_202F3455E6264E97929E12A8F9894788}

Check the methods in your SDK code that let you pass [!UICONTROL declared IDs] from Android and iOS mobile devices. The variable names for the Android and iOS code libraries are the same:

* `dpid`: The cross-device data source ID. 
* `dpuuid`: The [!UICONTROL declared ID] (i.e., the user ID).

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
    ```javascript
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    ```
    <p> <b>Example:</b> </p> 
    ````javascript
      [ADBMobile&nbsp;audienceSetDpid:@"290" 
      dpuuid:@"99301393923940"]; 
    ```
    </td> 
  </tr> 
 </tbody> 
</table>

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html). 
