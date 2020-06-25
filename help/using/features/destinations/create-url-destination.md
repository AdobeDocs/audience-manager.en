---
description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configure a URL Destination
feature: Destination Basics
---


# Configure a [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] makes pixel calls from a page to your [!DNL destination]. Follow these instructions to create a [!DNL URL] [!DNL destination] with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] [!DNL destination], go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

## Basic Information {#basic-info}

This section contains fields and options that start the [!DNL URL destination] creation process. To complete this section:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. Name the [!DNL destination]. Avoid abbreviations and special characters.
3. *(Optional)* Describe the [!DNL destination]. A concise description is an effective way to define or provide more information about a [!DNL destination].
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the [!DNL URL destination].
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
7. *(Optional)* Select an **[!UICONTROL Auto-fill Destination Mapping]**. Options include:
    * **[!UICONTROL Segment ID]**: Automatically adds and sends the segment ID to the [!DNL destination].
    * **[!UICONTROL Integration Code Value]**: Automatically adds and sends the segment integration code to the destination mapping. The integration code is a unique identifier created and used by the customer. It is limited to 255 characters, maximum.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](/help/using/features/destinations/add-data-export-labels.md) for details).
3. Click **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. This section is optional. To complete this section:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(Optional)* Select the **[!UICONTROL Serialize]** check box.
   This lets you send segments to a [!DNL destination] sequentially rather than making separate calls for each segment. Serialization helps make data transfers efficient. Selecting this check box exposes the URL and delimiter fields. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| Field | Description |
|--- |--- |
|[!UICONTROL Base URL]|The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Example: `https://www.myCompany.com/%alias%...`|
|[!UICONTROL Secure URL]|The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Example: `https://www.myCompany.com/%alias%...`|
|[!UICONTROL Delimiter]|The symbol that separates the segment variables in the [!DNL URL] string. This is usually a comma or semi-colon. Get this information from your destination partner.|

## [!UICONTROL Segment Mappings] {#segment-mappings}

This section lets you search for and add segments to your [!UICONTROL destination]. To complete this section:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In [!UICONTROL Edit Mapping]:
    * **[!UICONTROL Mappings]**: Provide the key-value pairs used by the segment. 
    * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**: Choose a start and end date for the [!DNL destination]. If the end date is blank, the [!DNL destination] never expires.
1. Click **[!UICONTROL Done]**.