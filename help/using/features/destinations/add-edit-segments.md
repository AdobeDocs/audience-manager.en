---
description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Add Data Export Controls to a Destination
---

# Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL [Destination Builder](/help/using/features/destinations/destination-builder.md)]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

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