---
description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Paused and Deleted Segments
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
---

# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.

## Access to the Pause and Delete Controls

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the Actions column). These features affect segments as described below.

## Paused Segment Functionality

A paused (deactivated) segment:

* Stops segmenting new, qualified users.
* Retains a user's segmentation status/membership (does not remove a user from the segment).
* Remains in the segment list and can be reactivated.
* Does not send data to associated destinations.
* Returns data in the available reports (up to the deactivation date).

## Deleted Segment Functionality

A deleted segment:

* Stops segmenting new, qualified users.
* Removes qualified users from segment membership.
* Is removed from the segment list.
* Cannot be undeleted.
* Does not send data to associated destinations.
* Does not return data in the available reports.

>[!NOTE]
>
>You can also pause and delete segments using an API method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md#concept_B512E6C3410A4304A672588A60A792B1).