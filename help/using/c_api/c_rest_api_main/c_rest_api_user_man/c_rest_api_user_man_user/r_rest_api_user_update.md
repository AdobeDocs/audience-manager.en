---
description: A PUT method to update a user.
seo-description: A PUT method to update a user.
seo-title: Update a User
solution: Audience Manager
title: Update a User
uuid: eb4864c4-ec94-4e7d-9357-8ed75447f309
index: y
internal: n
snippet: y
translate: y
---

# Update a User


>**Request** 

>` PUT /api/v1/users/<userId>` 

>**Sample Request Body** 
>
>```
>{ 
>  "username" : <string>,  
>  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
>  "firstName" : <string>, 
>  "lastName" : <string>, 
>  "emailAddress" : <string>, 
>  "title" : <string_may_be_null>, 
>  "phoneNumber" : <string_may_be_null>, 
>  "groups" : [<group_1_id>, ...] 
>}
>```
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
>  "groups" : [<group_1_id>, ...] 
> 
>}
>```
>Returns ` 409 Conflict` if the username is already taken. 
