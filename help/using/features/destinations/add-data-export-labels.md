---
description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Add Data Export Controls to a Destination
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
---
# Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] work with the [!DNL Export Controls] you set on a data source. [!DNL Data Export Labels] prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

To add export labels to a destination:

1. Click **[!UICONTROL Audience Data]**:
    * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/create-cookie-destination.md) or [Create a URL Destination](../../features/destinations/create-url-destination.md) for information.
    * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. Select a [!DNL Data Export Label]. Leave the check boxes blank if you don't want to set any export restrictions. Export labels include the following options:
    * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
    * **[!UICONTROL This destination may be used for on-site ad targeting]**
    * **[!UICONTROL This destination may be used for off-site ad targeting]**
    * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. Click **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Create a Data Source](../../features/manage-datasources.md#create-data-source)
