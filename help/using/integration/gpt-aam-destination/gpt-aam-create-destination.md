---
description: You can send qualified segments to DFP through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-description: You can send qualified segments to DFP through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Create a GPT Destination
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
---

# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## Destinations

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) that you want to share data with. [!UICONTROL Destination Builder] provides the tools that let you create and manage these data delivery processes. Audience Manager destination features are located in *[!UICONTROL Audience Data] > [!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## Basic Information

To complete the [!UICONTROL Basic Information] section:

1. Name the destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Cookie Configuration

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Cookie Name:** Provide a short, descriptive name for your cookie.
1. **Data Format:** Select the **[!UICONTROL "Single Key"]** option.
1. **Key:** Provide a key name.
1. **Serialize:** Select the **[!UICONTROL Enable]** checkbox.
1. **Serial Delimiter:** Use a comma only.

## Segment Mappings

To add a segment to a cookie destination:

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. To find a segment:

    * Option 1: Start typing a segment name in the search field. The field updates automatically based on entered text. Click **[!UICONTROL Add]** once you find the segment you want to use.
    * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Add Mappings:** In the mappings pop, enter the segment ID in the mappings field and click **[!UICONTROL Save]**.

1. Click **[!UICONTROL Done]**.