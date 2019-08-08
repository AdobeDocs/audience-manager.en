---
description: The Destination landing page lists all of your URL, cookie, and server-to-server destinations. It provides features that let you create, edit, search for, and report on destinations. The landing page is located in Audience Data > Destinations.
seo-description: The Destination landing page lists all of your URL, cookie, and server-to-server destinations. It provides features that let you create, edit, search for, and report on destinations. The landing page is located in Audience Data > Destinations.
seo-title: Manage Destinations
solution: Audience Manager
title: Manage Destinations
uuid: 6b66ff42-0075-49a7-a58f-7f8ea2295fdc
---

# Manage Destinations {#manage-destinations}

The [!UICONTROL Destination] landing page lists all of your [!DNL URL], cookie, and server-to-server destinations. It provides features that let you create, edit, search for, and report on destinations. The landing page is located in **[!UICONTROL Audience Data > Destinations]**. 

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

The default landing page lists your destinations, based on type. You can filter the destinations by using the four available tabs:

* **All**: shows all types of destinations.
* **Adobe Experience Cloud**: shows destinations which send data to other Adobe Experience Cloud solutions. Currently, the only supported option is Adobe Analytics. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Integrated Platforms**: shows people-based and device-based destinations (also named server-to-server destinations). Note that people-based destinations are currently a beta feature only available to selected customers.
* **Custom**: shows cookie and URL destinations. 


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Configure a URL Destination {#configure-url-destination}

A [!DNL URL] destination makes pixel calls from a page to your destination. Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Basic Information {#basic-info}

This section contains fields and options that start the URL destination creation process. To complete this section:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. Name the destination. Avoid abbreviations and special characters.
3. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the URL destination.
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
7. *(Optional)* Select an **[!UICONTROL Auto-fill Destination Mapping]**. Options include:
    * **[!UICONTROL Segment ID]**: Automatically adds and sends the segment ID to the destination.
    * **[!UICONTROL Integration Code Value]**: Automatically adds and sends the segment integration code to the destination mapping. The integration code is a unique identifier created and used by the customer. It is limited to 255 characters, maximum.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Click **[!UICONTROL Save]**.

### Configuration {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. This section is optional. To complete this section:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(Optional)* Select the **[!UICONTROL Serialize]** check box.
   This lets you send segments to a destination sequentially rather than making separate calls for each segment. Serialization helps make data transfers efficient. Selecting this check box exposes the URL and delimiter fields. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| Field | Description |
|--- |--- |
|Base URL|The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Example: `https://www.myCompany.com/%alias%...`|
|Secure URL|The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Example: `https://www.myCompany.com/%alias%...`|
|Delimiter|The symbol that separates the segment variables in the [!DNL URL] string. This is usually a comma or semi-colon. Get this information from your destination partner.|

### Segment Mappings {#segment-mappings}

This section lets you search for and add segments to your destination. To complete this section:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In [!UICONTROL Edit Mapping]:
    * **[!UICONTROL Mappings]**: Provide the key-value pairs used by the segment. 
    * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**: Choose a start and end date for the destination. If the end date is blank, the destination never expires.
1. Click **[!UICONTROL Done]**.

## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. Go to **[!UICONTROL Audience Data > Destinations]**. Select **Integrated Platforms > Device-Based** and find the [!DNL S2S] destination you want to work with.
2. In the [!UICONTROL Action] column, click the pencil icon to edit the destination.
   * In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * In [!UICONTROL Edit Mapping]:
        * **[!UICONTROL Mappings]**: Set a value for the [key-value pair](../../features/destinations/key-value-pairs.md) used by this destination.
        * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**: Choose a start and end date for the destination. If the end date is blank, the destination never expires.
3. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] work with the [!DNL Export Controls] you set on a data source. [!DNL Data Export Labels] prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

To add export labels to a destination:

1. Click **[!UICONTROL Audience Data]**:
    * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
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

>[!MORE_LIKE_THIS]
>
>* [Create a Data Source](../../features/manage-datasources.md#create-data-source)
