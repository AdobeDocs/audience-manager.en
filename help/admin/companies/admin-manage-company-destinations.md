---
description: Create, edit, and delete Audience Manager destinations.
seo-description: Create, edit, and delete Audience Manager destinations.
seo-title: Manage Company Destinations
title: Manage Company Destinations
uuid: d9a6bfb1-7629-44e0-b7d7-ece44f65ea2b
---

# Manage Company Destinations{#manage-company-destinations}

Create, edit, and delete Audience Manager destinations.

## Manage Company Destinations {#task_735DF86EC7B8417FBF4F968E1D823835}

Create, edit, and delete [!DNL Audience Manager] destinations.

<!-- 

t_company_destinations.xml

 -->

For detailed information, see [Destinations](https://microsite.omniture.com/t2/help/en_US/demdex/index.html#Destinations) in the *Audience Manager Users Guide*. 

## Create or Edit Company Destinations {#concept_E7BBEF3FB7954C1492701ADF55626C7A}

Scroll through the sections for step-by-step instructions on how to create new [!DNL Audience Manager] destinations or edit existing destinations.

<!-- 

create-edit-company-destinations.xml

 -->

Please visit the [Experience Cloud partner integration page](https://wiki.corp.adobe.com/x/mPIMPw) before setting up destinations. The page contains the specific information that you need to fill in for each [!DNL Audience Manager] partner integration.

If your client wants to use [!DNL Adobe Media Optimizer] as a destination in [!DNL Audience Manager] , you need to set this up in [!DNL Adobe Media Optimizer].

* [Navigate to the Destinations Tab](../companies/admin-manage-company-destinations.md#section_F19E06C8604E4B44B2442AD2D034721D) 
* [Basic Settings](../companies/admin-manage-company-destinations.md#section_EC8DF6F2182B474BA59963FC69DF1FB2) 
* [Realtime Data (for S2S destinations)](../companies/admin-manage-company-destinations.md#section_79ABA852B21A4D56961FB076CF4EB0F1) 
* [Batch Data](../companies/admin-manage-company-destinations.md#section_AFE5E4ADDA644967809198E4C495608E) 
* [Configure Data Sources](../companies/admin-manage-company-destinations.md#section_9DCE47FEA36F4AE1B34B85F12726F12E) 
* [Save and Finalize](../companies/admin-manage-company-destinations.md#section_BD56D255C4EA4DEBAE399DCCD6A200B7)

## Navigate to the Destinations Tab {#section_F19E06C8604E4B44B2442AD2D034721D}

1. Click **[!UICONTROL Companies]**, then locate and click the desired company to display its [!UICONTROL Profile] page. You can use the [!UICONTROL Search] box or the pagination controls at the bottom of the list to find the desired company. You can sort each column in ascending or descending order by clicking the desired column's header. 
1. Click the **[!UICONTROL Destinations]** tab. 
1. To create a new destination, click **[!UICONTROL Add Destination]**. Or To edit an existing destination, click the destination's name in the **[!UICONTROL Name]** column.

## Basic Settings {#section_EC8DF6F2182B474BA59963FC69DF1FB2}

Fill in the fields in the **[!UICONTROL Basic Settings]** window.

**Name:** (Required) Specify the name of this destination.

**Description:** Specify descriptive information about this destination.

**Type:** (Required) Select the desired destination type:

* **[!UICONTROL Bulk ID]**: Sync IDs between different platforms. 
* **[!UICONTROL Bulk Trait]**: Send trait information in bulk to different platforms. 
* **[!UICONTROL Bulk Segment]**: Send segment information in bulk to different platforms. 
* **[!UICONTROL S2S]**: Use server-to-server destinations to send real-time and batch data to different platforms.

**Auto-Fill Destination Mapping:** ( [!UICONTROL S2S] only) Select an option:

* **Segment ID:** If you select this setting, the destination value mapping is filled with the [!DNL Audience Manager] Segment ID. 

* **Integration Code Value:** If you select this setting, the destination value mapping is filled with the [!DNL Audience Manager] Segment integration code.

**User ID Key:** (Required) Select the desired user ID key for this destination from the drop-down list.

This ID is used as the master data source ID. This determines the user IDs to be outbounded in the file.

>[!NOTE]
>
>For the [!UICONTROL Bulk ID] destination type, you cannot use the [!DNL Audience Manager] [!UICONTROL User ID] or the [!DNL Adobe Experience Cloud] ID.

If your data source ID ( [!UICONTROL DPID]) does not display in the drop-down list, you must select the **[!UICONTROL Outbound]** checkbox at the data-source level on the [Data Source Settings page](https://marketing.adobe.com/resources/help/en_US/aam/create-datasource.html).

**Target Data Source:** (Required) Select the desired data source for this destination from the drop-down list. This setting enables labeling of outbounded data, which allows for ingestion into separate systems on the clients' side.

**Foreign Account ID:** Specify the foreign account ID for this destination. This is the identification value in the recipient's system for this outbounded data.

**Outbound Sample Rate Denominator:** When the total amount of returned data is unknown, use this setting to return only a sample amount of data, rather than the full amount. Adjust the number here to represent a fraction of the data (e.g., a value of '100' returns 1/100th the regular amount of data, a value of '10' returns 1/10th the regular amount of data). The default is '1', which returns all data.

## Realtime Data (for S2S destinations) {#section_79ABA852B21A4D56961FB076CF4EB0F1}

If you are creating an [!UICONTROL S2S] destination, fill in the fields below:

**[!UICONTROL Servers]**: Select the desired HTTP server for this destination.

**[!UICONTROL Format]**: Select the desired format for this destination from the drop-down list.: HTTP only.

>[!NOTE]
>
>For S2S only, you can enable or disable either [!UICONTROL Realtime] or [!UICONTROL Batch] destinations using the onscreen Off/On sliders. You cannot disable both options.

## Batch Data {#section_AFE5E4ADDA644967809198E4C495608E}

For [!UICONTROL Bulk ID], [!UICONTROL Bulk Trait] or [!UICONTROL Bulk Segment] destinations, fill in the fields below:

**[!UICONTROL Protocol]**: (Required) Select the desired protocol for this destination from the drop-down list:

* **[!UICONTROL FTP]** 
* **[!UICONTROL HTTP]** 
* **[!UICONTROL S3]**

**[!UICONTROL Servers]**: (Required) Select the desired server for this destination from the drop-down list.

**[!UICONTROL Format]**: (Required) Select the desired format for this destination from the drop-down list: HTTP or file type, depending on the protocol you chose above.

**[!UICONTROL Sync Type]**: (Required) Select the desired sync type for this destination. This indicates the level of user activities clients would want to include in the outbound orders. Select **[!UICONTROL Customer]** if clients are only interested in analyzing segment qualifications from their properties. Select **[!UICONTROL Platform]** if they want to include segment qualifications from off-site activities across all [!DNL Audience Manager] customers.

* **[!UICONTROL Customer]**: File contains active users that have at least 1 trait realization only on client's properties (associated with the client's PID) for the selected time period. Your clients should use this option to outbound their *real-time* segment qualifications to destinations. 

* **[!UICONTROL Platform]**: File contains active users that have at least 1 real-time interaction, be it ID sync or trait realization, anywhere across all [!DNL Audience Manager] clients' properties (associated with all client PIDs) for the selected time period. Your clients should use this option to outbound their *total* segment qualifications to destinations. 

* **[!UICONTROL Lifetime]**: File contains active users seen anywhere across all [!DNL Audience Manager] clients' properties since the creation of the destination.

**[!UICONTROL Sync Type Lookback Period]**: If you select [!UICONTROL Customer] or [!UICONTROL Platform], select a time period. Files contain active users for the selected time period.

Next, select the order type. This indicates the frequency and scope of each outbound integration with partners. Select between incremental and full orders.

**[!UICONTROL Incremental Scheduled Run]**: With each run, [!DNL Audience Manager] will only outbound the net new users qualified since the previous outbound order. Select the desired time period that you want [!DNL Audience Manager] to perform incremental synchronization processes. For example, you can select every 24 hours, every seven days, every 30 days, or never. 

>[!NOTE] {importance="high"}
>
>The first ever incremental order is equivalent to a full order because no previous users were ever sent to the destination.

**[!UICONTROL Full Sync Scheduled Run]**: With each run, [!DNL Audience Manager] will outbound all active users since the destination was first set up. Select the desired schedule that you want [!DNL Audience Manager] to use to perform full synchronization processes. For example, you can select every 24 hours, every seven days, every 30 days, or never. 

>[!NOTE] {importance="high"}
>
>We recommend using incremental syncs more frequently than full syncs. Incremental syncs only send files that contain new trait realizations or ID syncs. Full syncs send the all the files, whether or not they include new realizations or ID syncs. Only use the [!UICONTROL Full Sync Scheduled Run] configuration when clients need a full copy of all their users, to reduce the outbound data volume.

## Configure Data Sources {#section_9DCE47FEA36F4AE1B34B85F12726F12E}

For [!UICONTROL Bulk ID], [!UICONTROL Bulk Trait] or [!UICONTROL Bulk Segment] destinations, fill in the fields below. These settings let you send all data (traits, segments, or IDs, based on type selected) associated with the data sources.

**[!UICONTROL All Unrestricted First Party Data]**: Select to use all first-party data sources. If you select this option, the [!UICONTROL Available Data Sources] options are disabled.

**[!UICONTROL Available Data Sources]**: Use the arrows to move data sources between the **[!UICONTROL Available Data Sources]** and **[!UICONTROL In File Data Sources]** boxes.

## Save and Finalize {#section_BD56D255C4EA4DEBAE399DCCD6A200B7}

The **[!UICONTROL Save]** button is activated after filling in all the required fields. Click **[!UICONTROL Save]** to finalize the create destination process. 

## Delete Company Destinations {#concept_C9A94BDA24B64A8E82A2F3EC2C8F271A}

A step-by-step guide to deleting company destinations.

<!-- 

delete-company-destinations.xml

 -->

**To delete a destination:**

1. Click **[!UICONTROL Companies]**, locate and click the desired company, then click the **[!UICONTROL Destinations]** tab. 
1. Click  ![](assets/icon_delete.png) in the **[!UICONTROL Actions]** column of the desired destination. 
1. Click **[!UICONTROL OK]** to confirm the deletion.

>[!NOTE]
>
>You cannot delete a destination if it has segments mapped to it.

