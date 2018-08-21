---
description: To create a Profile Merge Rule, go to Audience Data > Profile Merge Rules > Add New Rule and complete the steps for each section described here. You can create up to 3 merge rules after setting up a cross-device data source. Administrator permissions are required to create, edit, or delete a rule. All users can view and use existing Profile Merge Rules.
seo-description: To create a Profile Merge Rule, go to Audience Data > Profile Merge Rules > Add New Rule and complete the steps for each section described here. You can create up to 3 merge rules after setting up a cross-device data source. Administrator permissions are required to create, edit, or delete a rule. All users can view and use existing Profile Merge Rules.
seo-title: Create a Profile Merge Rule
solution: Audience Manager
title: Create a Profile Merge Rule
uuid: 4aef2215-a347-4276-8984-5dbbcbb2fc9b
index: y
internal: n
snippet: y
translate: y
---

# Create a Profile Merge Rule

**Prerequisites:** A cross-device data source is required to build a [!UICONTROL  Profile Merge Rule]. See [ Create a Data Source ](../../../c_features/c_datasources/create-datasource.md#concept_3B7696B3EC77416492D3B99EBD79EA44). 


>[!TIP]
>
>See[ Profile Merge Rule Options Defined ](../../../c_features/profile-link-intro/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0) for descriptions of these different controls. 



## Basic Information {#section_A57B424647D647CF9687E99F21C318D7}

To complete the [!UICONTROL  Basic Information] section: 


1. Name the [!UICONTROL  Profile Merge Rule].
1. *(Optional)* Describe the [!UICONTROL  Profile Merge Rule]. A concise description helps you define the role or purpose of your rule.
1. *(Optional)* Select **[!UICONTROL  Set as default]** if you want to make this the default [!UICONTROL  Profile Merge Rule]. New segments are automatically associated with the default rule.


## Data Export Controls {#section_6B22BFF8BA724DC38852D3437A8C171E}

[ Data Export Controls ](../../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C) are optional classification rules you can apply to your [!UICONTROL  Profile Merge Rule]. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL  Data Export Controls]. 

## Profile Merge Rule Setup {#section_61EEF440AC384395B86C222EFA5EB9EF}

To complete the [!UICONTROL  Proflie Merge Rule Setup] section: 


1. Select an **[!UICONTROL  Authenticated Option]**. Options include: 
    * **[!UICONTROL  No Authenticated Profile]**
    * **[!UICONTROL  Current Authenticated Profile]**
    * **[!UICONTROL  Last Authenticated Profile]**


1. Select an **[!UICONTROL  Authenticated Profile Option]** (up to 3, maximum). These are the [ cross-device data sources ](../../../c_features/profile-link-intro/merge-rules-start/create-cross-device-datasource.md#concept_396828374D1B48C988655B2ED817F29B) you have created previously.
1. Select a **[!UICONTROL  Device Option]**. Options include: 
    * **[!UICONTROL  No Device Profile]**
    * **[!UICONTROL  Current Device Profile]**
    * **[!UICONTROL  Profile Link Device Graph]**
    * **[!UICONTROL  Device Co-op]**


1. Click **[!UICONTROL  Save]**.


## Next Steps {#section_0A2D9E025E9646B89BE2B7634BCE743F}

Review and complete the procedures described in [ Configure Merge Rule Code ](../../../c_features/profile-link-intro/merge-rules-start/merge-rules-configure-code.md#concept_169938D1988447E1B60896908A49C78A). 
>[!MORE_LIKE_THIS]
>
>* [ Profile Merge Rule Options Defined ](merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0)
