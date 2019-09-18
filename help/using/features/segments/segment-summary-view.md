---
description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Summary View
solution: Audience Manager
title: Segment Summary View
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
---

# Segment Summary View {#segment-summary-view}

The [!UICONTROL Segment Summary] page displays details such as name, traits in the segment, rules performance data, and destination mapping information.

Click a segment name from the main dashboard to access its summary page. Summary sections include:

1. **[!UICONTROL Basic Information]:** Shows required and optional details specified when the segment was created.
2. **[!UICONTROL Segment Graph]:** Displays performance data graphically and for fixed 1, 7, 14, 30, 60, and 90 day intervals. We explain segment population numbers in a [separate article](../../features/segments/segment-builder-data.md).

    ![segments-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** The report shows the number of people or households that qualify for a segment by counting the number of cross-device IDs and/or External Device Graph IDs that are linked to the devices that qualified for the segment (shown by the [!UICONTROL Total Segment Population]). The cross-device IDs and External Device Graph IDs shown in this report are used to merge profiles with the profile merge rule the segment is using. This report is displayed only if you selected a cross-device data source or an External Device Graph in the profile merge rule that the segment is using.

   ![segments-graph](assets/segment-type.png)

    >[!NOTE]
    >
    >Audience Manager only displays the [!UICONTROL Identity Type Breakdown] report if you have cross-device IDs qualified for the segment.

    >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** Lists traits in the segment along with qualification rules.
5. **[!UICONTROL Destination Mappings]:** Lists destination mappings for the segment.
6. **[!UICONTROL Management Tools]:** Controls that let you create, edit, clone, and delete segments.