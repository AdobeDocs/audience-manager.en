---
description: To create a cross-device data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create or edit a cross-device data source.
seo-description: To create a cross-device data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create or edit a cross-device data source.
seo-title: Create a Cross-Device Data Source
solution: Audience Manager
title: Create a Cross-Device Data Source
uuid: 61fcb950-b7f7-4412-8133-9f89f7329500
index: y
internal: n
snippet: y
translate: y
---

# Create a Cross-Device Data Source


>[!TIP]
>
>See[ Data Source Settings and Menu Options ](../../../c_features/c_datasources/datasource-settings-definitions.md#reference_A87B381067E04C26A426514AF3B64E64) for descriptions of these different controls. 



## Data Source Details {#section_D359CAAE0BEA4527B3A04855486033DE}

To complete the Data Source Details section: 


1. Name the data source.
1. *(Optional)* Describe the data source. A concise description helps you define the role or purpose of the data source.
1. Provide an integration code. An integration code is your own, unique ID for this data source.
1. In the **[!UICONTROL  ID Type]** list, select **[!UICONTROL  Cross Device]**.
1. In the **[!UICONTROL  ID Definition]** list, select an option that defines the data source type. Options include: 
    * **[!UICONTROL  Person]**: An ID that defines a single person. This ID can be mapped to multiple [!DNL  Audience Manager] IDs.
    * **[!UICONTROL  Household]**: An ID that defines a group of people. This ID can be mapped to multiple [!DNL  Audience Manager] IDs.




## Data Export Controls {#section_895821268F6F42E9A181B717DD6F1D04}

[ Data Export Controls ](../../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C) are optional classification rules you can apply to a data source and destination. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL  Data Export Controls]. 

## Data Source Settings {#section_928E1EB8EE7149A88F46ABD3B6FE5BAF}

[!UICONTROL  Data Source Settings] section provides multiple options, but these 2 are important for creating a cross-device data source: 


* **[!UICONTROL  Use as Authenticated Profile]**: Selected by default, this setting lets you build a [!UICONTROL  Profile Merge Rule] with your own, authenticated data.
* **[!UICONTROL  Use as a Device Graph]**: This control is available only to accounts listed as a data provider. Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL  Audience Manager] customers. Work with your [!DNL  Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL  Data Source] should be shared with. Your consultant will provision your account and device graph sharing through an internal provisioning processes.


The text fields associated with these settings let you rename the [!UICONTROL  Data Source] with an alias that appears in the [ Profile Merge Rule options ](../../../c_features/profile-link-intro/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0). For example, if you add an alias to **[!UICONTROL  Use as Authenticated Profile]**, that name appears in the [!UICONTROL  Authenticated Profile Options] list. If you add an alias to **[!UICONTROL  Use as a Device Graph]**, that name appears in the [!UICONTROL  Device Options] list. 
>[!MORE_LIKE_THIS]
>
>* [ Create a Data Source ](create-datasource.md#concept_3B7696B3EC77416492D3B99EBD79EA44)
