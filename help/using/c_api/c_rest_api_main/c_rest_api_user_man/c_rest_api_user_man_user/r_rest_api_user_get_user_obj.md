---
description: A Get method to return the user object for a User ID.
seo-description: A Get method to return the user object for a User ID.
seo-title: Return User Object for a User ID
solution: Audience Manager
title: Return User Object for a User ID
uuid: 01380113-bf0b-46e5-bb15-b111d1e2b8ea
index: y
internal: n
snippet: y
translate: y
---

# Return User Object for a User ID


>**Request** 

>` GET /api/v1/users/<userId>` 

>**Sample Response** 
>
>```
>{ 
>  "pid" : <integer>, 
>  "userId": <integer>, 
>  "username" : <string>,  
>  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
>  "firstName" : <string>, 
>  "lastName" : <string>, 
>  "emailAddress" : <string>, 
>  "title" : <string_may_be_null>, 
>  "phoneNumber" : <string_may_be_null>, 
>  "groups" : [<groupd_id_1>, ...] 
> 
>}
>```
