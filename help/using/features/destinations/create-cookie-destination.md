---
description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Configure a Cookie Destination
feature: Destination Basics
---

# Configure a Cookie Destination {#create-cookie-destination}

A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

## Basic Information {#basic-information}

This section contains fields and options that start the cookie destination creation process. To complete this section:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. Name the destination. Avoid abbreviations and special characters.
3. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. You cannot configure cookie destinations for native mobile environments, such as Android or iOS apps.
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
7. *(Optional)* Select an **[!UICONTROL Auto-fill Destination Mapping]**. Options include:
    * **[!UICONTROL Segment ID]**: Automatically adds and sends the segment ID to the destination.
    * **[!UICONTROL Integration Code Value]**: Automatically adds and sends the segment integration code to the destination mapping. The integration code is a unique identifier created and used by the customer. It is limited to 255 characters, maximum.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

## Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](/help/using/features/destinations/add-data-export-labels.md) for details).
3. Click **[!UICONTROL Save]**.

## Configuration {#configuration}

This section contains fields and options that let you set up the cookie for your destination.

>[!NOTE]
>
>[!DNL Audience Manager] encodes data written to the destination cookie. For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`. 

To complete this section:

1. Click **[!UICONTROL Configuration]** to expose the controls
1. Name the cookie. Avoid abbreviations and special characters.
1. Choose a data format option. These options let you choose the delimiters and separators for the key-value pairs that send segment data to a destination. Format options include:
    * **Single key:** Lets you set the key in a key-value pair. You'll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
    * **Multi key:** Lets you set the key and value for a key-value pair. You'll create the key-value pair after you select a segment in the Segment Mappings section below.
   See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Click **[!UICONTROL Save]**.

All other settings are optional. For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](/help/using/features/destinations/cookie-destination-options.md).

## Segment Mappings {#segments-mapping}

This section lets you search for and add segments to your destination. To complete this section:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** to browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In the [!UICONTROL Edit Mapping] dialog:
    * **[!UICONTROL Mapping]** lets you set a value for the key specified in the Configuration section above.
    * **[!UICONTROL Publish from]** lets you set start and end date for the destination. If the end date is blank, the destination never expires.
1. Click **[!UICONTROL Save]**.
1. Click **[!UICONTROL Done]**.