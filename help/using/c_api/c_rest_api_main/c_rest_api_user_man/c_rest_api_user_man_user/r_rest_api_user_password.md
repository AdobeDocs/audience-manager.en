---
description: A PUT method to update the currently logged-in user.
seo-description: A PUT method to update the currently logged-in user.
seo-title: Update Logged-In User Password
solution: Audience Manager
title: Update Logged-In User Password
uuid: 854b769c-003b-408a-bb66-e079ca27772f
index: y
internal: n
snippet: y
translate: y
---

# Update Logged-In User Password



>>[!NOTE]
>>
>>Whereas most API methods are only callable by partner admins, this method is callable by non-admin users.
>


>**Request** 

>` POST /users/self/update-password` 

>**Sample Request Body** 
>
>```
>{ "oldPassword" : "old password", "newPassword" : "new password" }
>```
>Returns ` 200 OK` if successful. Returns ` 400 Bad Request` if something is wrong with either password. 
