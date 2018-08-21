---
description: A GET method to list users.
seo-description: A GET method to list users.
seo-title: List Users
solution: Audience Manager
title: List Users
uuid: 728e5525-19ec-4921-8ef4-d15a9bb61a6e
index: y
internal: n
snippet: y
translate: y
---

# List Users


>**Request** 

>` GET /api/v1/users/` 

>You can specify multiple group IDs in the query parameters: 

>` GET /api/v1/users/?groupId=343&amp;groupdId=12` 

>This query returns a list of all users in the specified groups. 

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
>  "groups" : [<group_1_id>, ...] 
> 
>}
>```
