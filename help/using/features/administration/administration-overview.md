---
description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and AlgoModell).
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and AlgoModell).
seo-title: Administration
solution: Audience Manager
title: Administration
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
---

# Administration {#administration}

The options under the [!UICONTROL Administration] menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and [!UICONTROL AlgoModels]).

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control (RBAC)].

[!DNL Audience Manager] uses groups to assign permissions. Permissions are not assigned at the user level. Group permissions are tied to objects (traits, segments, etc.) and to actions you can perform on those objects (edit, view, etc.).

## Create Users {#task_89D190BA6A394B719A35CDA76899B957}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Username:** Specify a unique username for Audience Manager.
   * **First Name:** Specify the user's first name.
   * **Last Name:** Specify the user's last name.
   * **Email Address:** Specify the user's email address. [!DNL Audience Manager] does not send regular notification to users. [!DNL Audience Manager] administrators have access to users' email addresses and can manually email users as needed. For example, if a user forgets his or her password, the email address specified in this field is used to send a temporary password and instructions to reset the password.
   * **Phone Number:** Specify the user's phone number.
   * **Is Admin:** Specify if this user is an [!DNL Audience Manager] administrator. Admin users can manage users (create, edit, etc.) and groups (create, assign permissions, etc.). Non-admin users can control only their own user profiles, including editing their email addresses and resetting their own passwords. For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md#task_B622BDCE85824926AE88C6D132F9EDAE).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **Active:**  Active users can access [!DNL Audience Manager] and have the permissions granted by group membership.
   * **Deactivated:**  Deactivated users cannot access [!DNL Audience Manager] and do not have any permissions. If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **Expired:** A user's password is older than 90 days.
   * **Pending:** The user has a temporary password, either as after a password reset or as a brand new account, and they have not yet set a permanent password.
   * **Locked Out:** 5 incorrect login attempts will lock out a user.
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
  For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#task_3327F7C4A9834F1BA5007EDA279D40F2).
1. Click **[!UICONTROL Save]**.

## Create a Group {#task_3327F7C4A9834F1BA5007EDA279D40F2}  

A *group* is a collection of users that share access rights to destination, segment, and trait objects. You can limit groups to single objects only or give them broad access to combinations of different objects.

<!-- t_create_groups.xml -->

To create a group:

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. In [!UICONTROL Group Details]:
   * Name the group.
   * Provide a brief group description.
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md#concept_F9E9D1D1EFF34AA2AD025109DD741C86), or [destination](../../features/destinations/destinations.md#concept_5BDA346C376C4B719EA394108AB2735A) from **[!UICONTROL Add Object]**.
   This opens a permissions window for your selected object.
1. Select the check box for the permissions you want group members to have.
1. *(Optional)* Assign [Wild Card Permissions](../../features/administration/administration-overview.md#concept_29BA0C02C1864F3BBB1D322F8A400A2D) to the group.
1. Click **[!UICONTROL Save Group]**.

## Understanding [!UICONTROL Wild Card Permissions] {#concept_29BA0C02C1864F3BBB1D322F8A400A2D}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] give group members automatic access to each data source associated to a segment, destination, or trait. By comparison, regular permissions only lets you assign specific data sources to the one of these objects. And, when you add new data sources, group members don't get access to those new sources.

You have to open the group permissions and assign those new data sources to the group. [!UICONTROL Wild Card Permissions] let you avoid this manual data source update process. Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.
