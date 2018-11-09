---
description: Use the Integration Users page to view a list of users in your Audience Manager configuration. You can edit or delete existing users or create new users, providing that you have the appropriate user roles assigned.
seo-description: Use the Integration Users page to view a list of users in your Audience Manager configuration. You can edit or delete existing users or create new users, providing that you have the appropriate user roles assigned.
seo-title: Integration Users
title: Integration Users
uuid: d2a65110-59ca-4c1b-9f95-73166da3c25c
index: y
internal: n
snippet: y
---

# Integration Users{#integration-users}

Use the Integration Users page to view a list of users in your Audience Manager configuration. You can edit or delete existing users or create new users, providing that you have the appropriate user roles assigned.

## Integration Users {#concept_1D6AA60781084B399D66D00F11441B06}

Use the [!UICONTROL Integration Users] page to view a list of users in your Audience Manager configuration. You can edit or delete existing users or create new users, providing that you have the appropriate user roles assigned.

<!-- 

c_integration_users.xml

 -->

You can sort each column in ascending or descending order by clicking the desired column's header.

Use the [!UICONTROL Search] box or the pagination controls at the bottom of the list to find the desired user.

The following sections contain more information: 

## Create or Edit a User {#task_963A34F1307C4473AEA5E3F7E362982E}

Use the [!UICONTROL Integration Users] page in the Audience Manager [!UICONTROL Admin] tool to create a new user or to edit an existing user's account.

<!-- 

t_create_user.xml

 -->

>[!NOTE]
>
>You must have the [!UICONTROL CREATE_USER] role in order to create new users. You must have the [!UICONTROL EDIT_USER] role in order to edit existing users.

1. To create a new user, click **[!UICONTROL Integration Users]** > **[!UICONTROL Create a New User]**.

   Or

   To edit an existing user, click the desired user in the **[!UICONTROL Username]** column. 
1. Fill in the fields:

   **[!UICONTROL First Name]**: (Required) Specify the user's first name.

   **[!UICONTROL Last Name]**: (Required) Specify the user's last name.

   **[!UICONTROL Username]**: (Required) Specify the user's username.

   **[!UICONTROL Email Address]**: (Required) Specify the user's email address.

   **[!UICONTROL Phone Number]**: Specify the user's phone number.

   **[!UICONTROL IMS ID]**: Specify the user's [!UICONTROL Internet Messaging Service ID].

   **[!UICONTROL User Roles]**: Select the desired user roles:

* **[!UICONTROL DEXADMIN]**: Provides administrator access to perform tasks in the Audience Manager [!UICONTROL Admin] tool. If you do not select this option, you can choose individual roles. These roles let users perform tasks using API calls, but not in the Admin tool. 
* **[!UICONTROL CREATE_USERS]**: Lets users create new users using an API call. 
* **[!UICONTROL DELETE_USERS]**: Lets users delete existing users using an API call. 
* **[!UICONTROL EDIT_USERS]**: Lets users edit existing users using an API call. 
* **[!UICONTROL VIEW_USERS]**: Lets users view other users in your Audience Manager configuration using an API call. 
* **[!UICONTROL CREATE_PARTNERS]**: Lets users create Audience Manager partners using an API call. 
* **[!UICONTROL DELETE_PARTNERS]**: Lets users delete Audience Manager partners using an API call. 
* **[!UICONTROL EDIT_PARTNERS]**: Lets users edit Audience Manager partners using an API call. 
* **[!UICONTROL VIEW_PARNTERS]**: Lets users view Audience Manager partners using an API call.

   **Status: **Select **[!UICONTROL Active]** to make this user an activated Audience Manager user. 
1. Click **[!UICONTROL Submit]**.

## Delete a User {#task_4AE38838D3F2485592A2B4756859AEA6}

Use the [!UICONTROL Integration Users] page in the Audience Manager [!UICONTROL Admin] tool to delete an existing user.

<!-- 

t_delete_user.xml

 -->

>[!NOTE]
>
>You must have the **[!UICONTROL DELETE_USER]** role in order to create new users.

1. To delete an existing user, click **[!UICONTROL Integration Users]**.
1. Click  ![](assets/icon_delete.png) in the **[!UICONTROL Actions]** column of the desired user.
1. Click **[!UICONTROL OK]** to confirm the deletion.
