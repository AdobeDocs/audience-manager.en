---
description: Create, edit, and delete folder traits.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Manage Folder Traits
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
---

# Manage Folder Traits {#manage-folder-traits}

Create, edit, and delete folder traits.

## Create a Folder Trait {#task_08E0B888675440AB9418E47ED0A7A771}

A folder trait is created automatically when you create a new folder in your taxonomy.

<!-- 
create-folder-trait.xml
-->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. In the [!UICONTROL Trait Storage] window, hover over:
    * "All Traits" text to add a new root level folder.
    * An existing parent folder to add a new subordinate folder.
    ![](assets/folder_traits_create.PNG)
1. Click the + icon to create the folder. Note that you can create a maximum of 2.000 folders in your taxonomy. See the [usage limits](../../features/administration/usage-limits.md#concept_54772E0557C74849812CE54ACB4B0511) documentation for more information.
1. Name the folder and click **Save**. For example, a folder named Electronics will have a folder trait named 'Electronics Folder Trait'. You can view and select the new folder trait in the traits dashboard.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control (RBAC)] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#task_7B1959B7BCFA4409BECDBAAC94A65771).

## Edit a Folder Trait {#task_7B1959B7BCFA4409BECDBAAC94A65771}

Describes how you can edit a folder trait.

<!--
edit-folder-trait.xml
-->

1. In the Traits dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. Click the pencil to edit the trait.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** workflow allows you to change the data source for folder traits. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by DPID, in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#section_FB11C9F6F6F542328A6F1F22C40C2220) to traits data sources.

>[!NOTE]
>
>You cannot directly rename a folder trait. [Rename its associated storage folder](../../features/traits/trait-storage.md#task_0A123EBA0E7D4DC68C027936CBC77711) in order to change the name of the folder trait.

## Delete a Folder Trait {#task_D8C06B8EB28A4EB98A37747638490368}

Delete a folder trait by deleting the storage folder that the trait belongs to.

<!--
delete-folder-trait.xml
-->

1. **Audience Data > Traits** to navigate to the **Traits** dashboard.
1. In the Trait Storage window, delete a folder by hovering over it and clicking the X icon.

   ![Step Result](assets/folder_traits_create.PNG)

>[!NOTE]
>
>You cannot delete a folder trait, if it is used in a segment expression. Navigate to the [trait view](../../features/traits/trait-details-page.md#concept_1117822DC9D94E25888A9D41DE01B1D9) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md#concept_D0C06175AB1C4220A407187D85FE6AFA), which allows you to remove traits from segment expressions.