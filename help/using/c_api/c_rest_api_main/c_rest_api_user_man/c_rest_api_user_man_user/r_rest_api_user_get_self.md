---
description: A Get method to return the user object for the currently logged-in user.
seo-description: A Get method to return the user object for the currently logged-in user.
seo-title: Return User Object for Logged-In User
solution: Audience Manager
title: Return User Object for Logged-In User
uuid: 07d0c18d-e440-4892-b985-f23843d2b1d0
index: y
internal: n
snippet: y
translate: y
---

# Return User Object for Logged-In User



>>[!NOTE]
>>
>>Whereas most API methods are only callable by partner admins, this method is callable by non-admin users.
>


>**Request** 

>` GET /api/v1/users/self` 

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
