---
description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
keywords: cdf;custom data feed
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Create a Data Source
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
---

# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Administrator permissions are required to create a data source.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Name the data source.
1. *(Optional)* Describe the data source. A concise description helps you define the role or purpose of the data source.
1. Provide an integration code. Generally, integration codes are optional. They are required when you want to:

    * [Create a cross-device data source](../features/profile-merge-rules/merge-rules-start.md#create-data-source). 
    * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). 
    * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md#concept_34A9CEA00B24447EBF7EA8DA2928E1DD).

1. Choose an **[!UICONTROL ID Type]**. ID Type options include:

    * **[!UICONTROL Cookie]**
    * **[!UICONTROL Device Advertising ID]**
    * **[!UICONTROL Cross-device]** (Required to create a [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Options include:

    * **[!UICONTROL Person]**
    * **[!UICONTROL Household]**

## Data Export Controls {#export-controls}

[Data Export Controls](../features/data-export-controls.md) are optional classification rules you can apply to a data source and destination. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

These settings determine how a data source is identified, used, and shared. You can also enable error reporting for inbound data files. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Click **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options)

## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a data source that you no longer need.

>[!NOTE]
>
>Please note the following restrictions:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md#concept_7D3F4AF1FAD440509956632B8A51E64D). 
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.

1. Click **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Select the check box next to one or more data sources.
   You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list. 
1. Click  ![](assets/icon_trash.png), then confirm the deletion.