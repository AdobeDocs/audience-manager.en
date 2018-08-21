---
description: Create users in Audience Manager and specify user details, login status, and assign users to groups.
seo-description: Create users in Audience Manager and specify user details, login status, and assign users to groups.
seo-title: Create Users
solution: Audience Manager
title: Create Users
topic: DIL API
uuid: c44cd5a9-7097-4d5a-aab0-65509a1d38ba
index: y
internal: n
snippet: y
translate: y
---

# Create Users


>1. Click **[!UICONTROL  Administration]** > **[!UICONTROL  User Management]** > **[!UICONTROL  Users]**.
>1. Click  ![](assets/icon_add.png) to display the [!UICONTROL  User Add] page.
>1. Under **[!UICONTROL  User Details]**, fill in the fields:

>       **Username: **Specify a unique username for Audience Manager. 

>       **First Name: **Specify the user's first name. 

>       **Last Name: **Specify the user's last name. 

>       **Email Address: **Specify the user's email address. Audience Manager does not send regular notification to users. Audience Manager administrators have access to users' email addresses and can manually email users as needed. For example, if a user forgets his or her password, the email address specified in this field is used to send a temporary password and instructions to reset the password. 

>       **Phone Number: **Specify the user's phone number. 

>       **Is Admin: **Specify if this user is an Audience Manager administrator. Admin users can manage users (create, edit, etc.) and groups (create, assign permissions, etc.). Non-admin users can control only their own user profiles, including editing their email addresses and resetting their own passwords. For more information, see [ Edit Your Account Settings](../../c_features/c_administration/t_edit_account_settings.md#task_B622BDCE85824926AE88C6D132F9EDAE). 
>1. Under **[!UICONTROL  Login]**, select the desired status:

>       **Active: ** Active users can access Audience Manager and have the permissions granted by group membership. 

>       **Deactivated: ** Deactivated users cannot access Audience Manager and do not have any permissions. If you deactivate users, their user information remains in Audience Manager and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use Audience Manager again in the future. 

>       **Expired:** A user's password is older than 90 days. 

>       **Pending:** The user has a temporary password, either as after a password reset or as a brand new account, and they have not yet set a permanent password. 

>       **Locked Out:** 5 incorrect login attempts will lock out a user. 
>1. Under **[!UICONTROL  Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.

>       For more information about groups and permissions, see [ Create a Group](../../c_features/c_administration/t_create_groups.md#task_3327F7C4A9834F1BA5007EDA279D40F2). 
>1. Click **[!UICONTROL  Save]**.
