---
description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Paused and Deleted Segments
uuid: 8a5856cc-2215-447a-a237-a10e32a05d40
index: y
internal: n
snippet: y
translate: y
---

# Paused and Deleted Segments

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.

 **Access to the Pause and Delete Controls**

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the Actions column). These features affect segments as described below.

**Paused Segment Functionality**

A paused (deactivated) segment:

* Stops segmenting new, qualified users. 
* Retains a user's segmentation status/membership (does not remove a user from the segment). 
* Remains in the segment list and can be reactivated. 
* Does not send data to associated destinations. 
* Returns data in the available reports (up to the deactivation date).

**Deleted Segment Functionality**

A deleted segment:

* Stops segmenting new, qualified users. 
* Removes qualified users from segment membership . 
* Is removed from the segment list. 
* Cannot be undeleted. 
* Does not send data to associated destinations. 
* Does not return data in the available reports.

>[!NOTE]
>
>You can also pause and delete segments using an API method. For more information, see [REST APIs](../../c_api/c_rest_api_main/c_rest_api_main.md#concept_B512E6C3410A4304A672588A60A792B1).

