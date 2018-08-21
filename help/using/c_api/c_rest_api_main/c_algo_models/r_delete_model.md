---
description: A DELETE method that removes a model from your collection.
seo-description: A DELETE method that removes a model from your collection.
seo-title: Delete a Model
solution: Audience Manager
title: Delete a Model
uuid: 6077c42c-cfbb-4014-8082-ac40d92c59b2
index: y
internal: n
snippet: y
translate: y
---

# Delete a Model


>**Request** 

>` DELETE https://api.demdex.com/v1/models/ *` <model-id>`*` 

>**Sample Response** 

>Returns response code ` 204 No Content` if successful. Returns ` 400 Bad Request` if there are any active traits created with this model and returns those trait IDs in an array. Remove traits from the model (or delete them) before you delete a model. 
