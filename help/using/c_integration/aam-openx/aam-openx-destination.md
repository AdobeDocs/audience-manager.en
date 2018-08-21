---
description: Create a cookie-based destination for OpenX in Audience Management.
seo-description: Create a cookie-based destination for OpenX in Audience Management.
seo-title: Create an OpenX Destination
solution: Audience Manager
title: Create an OpenX Destination
uuid: ff13bfc3-4a23-4a43-88c1-4c9e668e87bf
index: y
internal: n
snippet: y
translate: y
---

# Create an OpenX Destination

In Audience Manager, a *destination* is any other system (ad server, DSP, ad network, etc.) that you want to share data with. [!UICONTROL  Destination Builder] provides the tools that let you create and manage these data delivery processes. Audience Manager destination features are located in *Audience Data > Destinations*. To get started, click **[!UICONTROL  Add New Destination]** and follow the steps below. 

**Step 1: Basic Information** 

To complete the [!UICONTROL  Basic Information] section: 
1. Name the destination.
1. Select **[!UICONTROL  "Cookie"]** from the [!UICONTROL  Type] drop-down list.
1. Click **[!UICONTROL  Next]** and move on to the [!UICONTROL  Configuration] and [!UICONTROL  Segment Mappings] sections.


**Step 2: Configuration Information** 

To complete the [!UICONTROL  Configuration] section: 

1. **Cookie Name:** Provide a short, descriptive name for your cookie.
1. **Cookie Domain: **Leave blank to set a cookie in the domain of the user's current page. If you want to specify a domain, prefix the name with a period like this, ` .mydomain.com`.
1. Choose a key option in the [!UICONTROL  Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL  Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL  Save]** and expand the [!UICONTROL  Segment Mappings] section.
**Step 3: Segment Mappings** 

To add a segment to a cookie destination: 

1. **Find segments:** The [!UICONTROL  Segment Mappings] section provides two search tools to help locate segments. To find a segment: 
    * Option 1: Start typing a segment name in the search field. The field updates automatically based on the text. Click **[!UICONTROL  Add]** once you find the segment you want to use.
    * Option 2: Click **[!UICONTROL  Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL  Add Selected Segments]** when done.

1. **Add Mappings:** In the mappings pop, enter the segment ID in the mappings field and click **[!UICONTROL  Save]**.
1. Click **[!UICONTROL  Done]**.
