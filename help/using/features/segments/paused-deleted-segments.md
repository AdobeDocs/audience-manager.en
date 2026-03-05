---
description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Paused and Deleted Segments
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
    internal-label: REST APIs
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## Access to the Pause and Delete Controls

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). These features affect segments as described below.

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
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).
