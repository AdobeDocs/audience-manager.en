---
description: A PUT method to update the currently logged-in user.
seo-description: A PUT method to update the currently logged-in user.
seo-title: Update Logged-In User
solution: Audience Manager
title: Update Logged-In User
uuid: f3adbff9-a2f7-45e8-a5e7-e21331428ad0
index: y
internal: n
snippet: y
translate: y
---

# Update Logged-In User



>>[!NOTE]
>>
>>Whereas most API methods are only callable by partner admins, this method is callable by non-admin users.
>


>**Request** 

>` PUT /self/update` 

>**Sample Request Body** 
>
>```
>{ 
>  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED">
>  "firstName" : <string>,
>  "lastName" : <string>,
>  "emailAddress" : <string>,
>  "title" : <string_may_be_null>,
>  "phoneNumber" : <string_may_be_null>
>}
>```
>**Sample Response** 
>
>```
>{
>  "userId": <integer>,, 
>  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED">
>  "firstName" : <string>,
>  "lastName" : <string>,
>  "emailAddress" : <string>
>  "title" : <string_may_be_null>,
>  "phoneNumber" : <string_may_be_null>
>}
>```
>Returns ` 409 Conflict` if the username is already taken. 
