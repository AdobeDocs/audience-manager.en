---
description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Create a Data Source
uuid: 769a43e7-0e1b-43b6-ad3e-6eb9dd359e10
index: y
internal: n
snippet: y
translate: y
---

# Create a Data Source


>[!TIP]
>
>See[ Data Source Settings and Menu Options ](../../c_features/c_datasources/datasource-settings-definitions.md#reference_A87B381067E04C26A426514AF3B64E64) for descriptions of these different controls. 



## Data Source Details {#section_D359CAAE0BEA4527B3A04855486033DE}

To complete the Data Source Details section: 


1. Name the data source.
1. *(Optional)* Describe the data source. A concise description helps you define the role or purpose of the data source.
1. Provide an integration code. Generally, integration codes are optional. They are required when you want to: 
    * [ Create a cross-device data source ](../../c_features/profile-link-intro/merge-rules-start/create-cross-device-datasource.md#concept_3B7696B3EC77416492D3B99EBD79EA44).
    * Use the [ Experience Cloud ID service ](https://marketing.adobe.com/resources/help/en_US/mcvid/).
    * Work with [ Profile Merge Rules ](../../c_features/profile-link-intro/merge-rules-start/merge-rules-start.md#concept_34A9CEA00B24447EBF7EA8DA2928E1DD).


1. Choose an **[!UICONTROL  ID Type]**. ID Type options include: 
    * **[!UICONTROL  Cookie]**
    * **[!UICONTROL  Device Advertising ID]**
    * **[!UICONTROL  Cross-device]** (Required to create a [!UICONTROL  Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL  ID Definition]** options.


1. Choose an **[!UICONTROL  ID Definition]** option. Options include: 
    * **[!UICONTROL  Person]**
    * **[!UICONTROL  Household]**




<!-- <p> 
 <note>
   Selecting 
  <span class="uicontrol"> Device Advertising ID </span> or 
  <span class="uicontrol"> Cross Device </span> limits the inbound ID options in the Data Source Settings section to 
  <span class="uicontrol"> Customer ID </span> only. 
 </note> </p> -->

## Data Export Controls {#section_895821268F6F42E9A181B717DD6F1D04}

[ Data Export Controls ](../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C) are optional classification rules you can apply to a data source and destination. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use Data Export Controls. 

## Data Source Settings {#section_928E1EB8EE7149A88F46ABD3B6FE5BAF}

These settings determine how a data source is identified, used, and shared. You can also enable error reporting for inbound data files. To complete the Data Source Settings section: 


1. Select a Data Source Setting check box to apply an option to your data source.
1. Click **[!UICONTROL  Save]**.

>[!MORE_LIKE_THIS]
>
>* [ Data Source Settings and Menu Options ](datasource-settings-definitions.md#reference_A87B381067E04C26A426514AF3B64E64)
