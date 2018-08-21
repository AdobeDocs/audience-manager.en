---
description: A POST method to create a new user.
seo-description: A POST method to create a new user.
seo-title: Create a User
solution: Audience Manager
title: Create a User
uuid: 87ce5b0e-2799-4f97-8f9b-7d3a2934b276
index: y
internal: n
snippet: y
translate: y
---

# Create a User


>**Request** 

>` POST /api/v1/users/` 

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
>  "groups" : [<group_1_id>, ...],
>  "isAdmin" : true | false
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
>  "title" : <string_may_be_null>,
>  "phoneNumber" : <string_may_be_null>,
>  "groups" : [<group_1_id>, ...],
>  "isAdmin" : <"true"|"false">
>
>}
>```
>If isAdmin is set to true, the user is created as a partner admin. This property also lets you know whether a user is a partner admin. 

>Returns ` 409 Conflict` if the username is already taken. 
