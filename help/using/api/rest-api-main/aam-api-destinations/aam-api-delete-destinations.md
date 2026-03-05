---
description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Delete Destinations
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
TQID: https://experienceleague.adobe.com/hONQoLCrSxcMnDY7yPf-RX22Etj3WIykBhKEx1IyRMo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
---
# Delete Destinations {#delete-destinations}

`DELETE` and `POST` methods that let you remove destinations and segment mappings.

<!-- r_delete_destinations_all.xml -->

## Delete a Destination

A `DELETE` method that removes a destination.

>[!NOTE]
>
>You must remove all segment mappings before you can delete a destination.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## Bulk Delete Destinations

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* Request: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## Delete Destination Mappings by Segment Mapping ID

A `POST` method that removes destination mappings according to the specified segment ID.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.
