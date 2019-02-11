---
description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: User Management API Methods
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
---

# User Management API Methods {#user-management-api-methods}

Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.

<!--
c_rest_api_user_man_user.xml
-->

## Create a User {#reference_791EAD47150C4112AAC3D687E91666CF}

A `POST` method to create a new user.

<!--
r_rest_api_user_create.xml
-->

### Request

`POST /api/v1/users/`

### Sample Request Body

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Response

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

If `isAdmin` is set to true, the user is created as a partner admin. This property also lets you know whether a user is a partner admin.

Returns `409 Conflict` if the username is already taken.

## Update a User {#reference_48437AAB1C224812BB506C79201A0CE2}

A `PUT` method to update a user.

<!--
r_rest_api_user_update.xml
-->

### Request

`PUT /api/v1/users/`*`<userId>`*

### Sample Request Body

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Response

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User {#reference_FFDBAF743D7848ADBA2D659F487E5063}

A `PUT` method to update the currently logged-in user.

<!--
r_rest_api_user_update_self.xml
-->

>[!NOTE]
>
>Whereas most API methods are only callable by partner admins, this method is callable by non-admin users.

### Request

`PUT /self/update`

### Sample Request Body

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Response

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User Password {#reference_FD6C65E07E6A4D619C466328BC46574A}

A `PUT` method to update the currently logged-in user.

<!--
r_rest_api_user_password.xml
-->

>[!NOTE]
>
>Whereas most API methods are only callable by partner admins, this method is callable by non-admin users.

### Request

`POST /users/self/update-password`

### Sample Request Body

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returns `200 OK` if successful. Returns `400 Bad Request` if something is wrong with either password.

## Reset Logged-In User Password {#reference_B8B26AC89832485D95509DAFB9F84C12}

A `PUT` method to reset the currently logged-in user. Audience Management sends the user a system-generated password.

<!--
r_rest_api_user_password_reset.xml
-->

>[!NOTE]
>
>Whereas most [!UICONTROL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Request

`POST /self/reset-password`

Returns `200 OK` if successful.

## Return User Object for a User ID {#reference_A88F770E70CE450BB861A48A422D5F83}

A `Get` method to return the user object for a User ID.

<!--
r_rest_api_user_get_user_obj.xml
-->

### Request

`GET /api/v1/users/`*`<userId>`*

### Response

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Return User Object for Logged-In User {#reference_09DA0C887F144D66AFEE2358A168C9A3}

A `Get` method to return the user object for the currently logged-in user.

<!--
r_rest_api_user_get_self.xml
-->

>[!NOTE]
>
>Whereas most [!UICONTROL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Request

`GET /api/v1/users/self`

### Response

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## List Users {#reference_B8F8C13E96A64699B17D43E0F68F1202}

A `GET` method to list users.

<!--
r_rest_api_user_list.xml
-->

### Request

`GET /api/v1/users/`

You can specify multiple group IDs in the query parameters:

`GET /api/v1/users/?groupId=343&groupdId=12`

This query returns a list of all users in the specified groups.

### Response

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "emailAddress" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Delete a User {#reference_21157FBE8CAC4827853B0E4A2639890F}

A `DELETE` method to delete a user.

<!--
r_rest_api_user_delete.xml
-->

### Request

`DELETE /api/v1/users/`*`<user_id>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Users in Bulk {#reference_3F0D4F1E2FFC4AF1A53C33D1FC929CE2}

A `POST` method to delete multiple users in bulk.

<!-- 
r_rest_api_user_delete_bulk.xml
-->

### Request

`POST /api/v1/users/bulk-delete`

### Sample Request Body

```
{[<user_id_1>, <user_id_2>, ...]}
```