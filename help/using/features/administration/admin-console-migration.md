---
description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager User Migration to Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
---
# [!DNL Audience Manager] user migration to [!DNL Admin Console] {#user-migration}

## Overview {#overview}

[!DNL Audience Manager] user account management is moving to the [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html), for a more streamlined experience across your Adobe solutions.

The benefits of using the [!DNL Admin Console] include:

|Benefit|Description|
|---|---|
| Single sign-on across solutions | [!DNL Audience Manager] users can sign in to [!DNL Experience Cloud] and all other solutions using their [!DNL Adobe ID] or [!DNL Enterprise ID]. This sign-in enables access to integrated solutions and core services across [!DNL Experience Cloud]. After the migration, users who attempt to sign in via legacy logins (`bank.demdex.com`) will be redirected to `experiencecloud.adobe.com`. |
| Manage users and groups | Once the migration is complete, [!DNL Audience Manager] administrators will manage users and groups exclusively in the [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/).|
|Manage products and services | From the [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), administrators can: <ul><li>Create, update, and remove users</li><li>Grant access to solutions and services</li></ul> |

To facilitate user migration, we are asking all [!DNL Audience Manager] administrators to start migrating their user accounts to [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) as soon as possible, by following the steps described in this article.

## What users need to do {#what-to-do-users}

As an Audience Manager user, all you need to do is contact your [!DNL Audience Manager] administrator and ask them to create a new user account for you in [!DNL Admin Console].

## What administrators need to do {#what-to-do-admins}

Audience Manager administrators should follow the steps below to migrate users to [!DNL Admin Console].

1. Go to [https://adminconsole.adobe.com](https://adminconsole.adobe.com) and log in using your Adobe ID or Enterprise ID. If you don't have access to the [!DNL Admin Console], contact Customer Care or your Adobe consultant.
2. Check the [!DNL Adobe Admin Console] [help guide](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) for detailed instructions on how to create and manage user accounts.
3. Create new user accounts for all your existing Audience Manager users.
4. Inform your users about the newly created user accounts. Once users are migrated to [!DNL Admin Console], they should stop using legacy logins.

## User migration considerations {#considerations}

Both users and administrators should keep in mind the following considerations for Audience Manager user migration:

* Once new user accounts are created in Admin Console, their existing permissions from their legacy user accounts will still apply.
* Updates to user permissions will still be managed from [!DNL Audience Manager]. The [!DNL Admin Console] only covers user and group management.
* Administrators do not need to disable legacy user accounts. Old user accounts will automatically be merged into the migrated ones.
