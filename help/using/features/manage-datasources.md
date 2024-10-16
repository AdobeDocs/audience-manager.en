---
description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
keywords: data sources;manage data source;audience manager data source
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Manage Data Sources
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
---
# Manage [!UICONTROL Data Sources] {#manage-data-sources}

## Create a [!UICONTROL Data Source] {#create-data-source}

To create a new [!UICONTROL data source], go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Administrator permissions are required to create a [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## [!UICONTROL Data Source] Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Name the [!UICONTROL data source].
1. *(Optional)* Describe the [!UICONTROL data source]. A concise description helps you define the role or purpose of the [!UICONTROL data source].
1. Provide an [!UICONTROL integration code]. Generally, [!UICONTROL integration codes] are optional. They are required when you want to:

    * [Create a cross-device data source](../features/profile-merge-rules/merge-rules-start.md#create-data-source). 
    * Use the [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). 
    * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. [!UICONTROL ID Type] options include:

    * **[!UICONTROL Cookie]**
    * **[!UICONTROL Device Advertising ID]**
    * **[!UICONTROL Cross-device]** (Required to create a [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

    >[!NOTE]
    >
    >If you want to export segments to Experience Platform, you must first create an individual cross-device [identity namespace](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) from the Experience Platform UI. The namespace name in Audience Manager must match the identity symbol in Experience Platform. This is a one-time configuration for each newly created data source in Audience Manager that you want to use to export segments to Experience Platform. 


1. Choose an **[!UICONTROL ID Definition]** option. Options include:

    * **[!UICONTROL Person]**
    * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Data Export Controls](../features/data-export-controls.md) are optional classification rules you can apply to a [!UICONTROL data source] and [!UICONTROL destination]. They prevent you from sending data to a [!UICONTROL destination] when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Settings {#settings}

These settings determine how a [!UICONTROL data source] is identified, used, and shared. You can also enable error reporting for inbound data files. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your [!UICONTROL data source].
2. Click **[!UICONTROL Save]**.

## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a [!UICONTROL data source] that you no longer need.

>[!NOTE]
>
>Please note the following restrictions:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md). 
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) to unmap these data sources.

1. Click **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Select the check box next to one or more data sources.
   You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list. 
1. Click  ![](assets/icon_trash.png), then confirm the deletion.


>[!MORELIKETHIS]
>
>* [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options)
