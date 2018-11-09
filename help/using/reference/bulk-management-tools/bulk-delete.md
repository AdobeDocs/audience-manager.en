---
description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Bulk Delete
uuid: 973c6428-0e7d-444a-a625-1fb98570db06
index: y
internal: n
snippet: y
---

# Bulk Delete{#bulk-delete}

Bulk delete lets you remove multiple segments, traits, folders, derived signals, and destinations with a single operation. Follow these instructions to make a bulk delete request.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools]* are not* supported by [!DNL Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [Audience Manager APIs](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_api.html) instead. [RBAC group permissions](../../c-features/c-administration/c-administration.md#concept_A606A162611E4256BB80F60715282296) assigned in the Audience Manager UI are honored in the Bulk Management Tools.

>[!NOTE]
>
>A bulk delete for destination mappings will fail if you have segments mapped to the destination. Remove your segments from that destination in the user interface before attempting to bulk delete destinations. Also, trait and segment folders must be empty before you can delete them.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and: 

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Delete]** tab.
1. Paste the delete headers into the first row of the update worksheet.
1. Paste or type the IDs for the objects you want to delete in the column below the header.
1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#section_6FE9BADB30254A4FADC77D2DCFB6A1EE) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns a message that indicates if the item has been deleted or an error message. Before entering data, your bulk update worksheet should look similar to the following: 
>
>![](assets/delete.png)>
>If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md#reference_1A3E7E0CEF6A4D8D801BC363A3C30C1A). 

