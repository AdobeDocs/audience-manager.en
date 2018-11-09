---
description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Delete Destinations
uuid: 08a424e0-e847-44ba-aa9b-3a966234683f
index: y
internal: n
snippet: y
---

# Delete Destinations{#delete-destinations}

DELETE and POST methods that let you remove destinations and segment mappings.

<!-- 

r_delete_destinations_all.xml

 -->

**Delete a Destination**

A `DELETE` method that removes a destination. 

>[!NOTE]
>
>You must remove all segment mappings before you can delete a destination.

* Request: `DELETE https://api.demdex.com/v1/destinations/ *`<destinationId>`*` 
* Response: Returns code `204 No Content` if successful.

**Bulk Delete Destinations**

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* Request: `POST https://api.demdex.com/v1/destinations/bulk-delete/` 
* Response: Returns code `204 No Content` if successful.

**Delete Destination Mappings by Segment Mapping ID** 
A `POST` method that removes destination mappings according to the specified segment ID.

* Request: `DELETE https://api.demdex.com/v1/destinations/ *`<destinationId>`*/segments/ *`<mappingId>`*` 
* Response: Returns code `204 No Content` if successful.

