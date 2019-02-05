---
description: A bulk update lets you edit multiple segments, traits, and segment or trait folders elements in a single operation. Follow these instructions to make bulk updates.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, and segment or trait folders elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Bulk Updates
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
---

# Bulk Updates{#bulk-updates}

A bulk update lets you edit multiple segments, traits, and segment or trait folders elements in a single operation. Follow these instructions to make bulk updates.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and: 

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Paste the update headers into the first row of the update worksheet. Note the following:

    * When updating a folder, all headers are required. 
    * When updating segments or traits, you only need the segment ID (SID) and the header element that needs to be changed. Delete unused headers.

1. Paste or type the data you want to change into a corresponding column based on the header label.
1. In the worksheet toolbar, click an update button that matches the        item you're updating.
   This action opens the [!UICONTROL Account Information] dialog box. 

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#section_6FE9BADB30254A4FADC77D2DCFB6A1EE) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md#concept_B512E6C3410A4304A672588A60A792B1) for examples. Before entering data, your bulk update worksheet should look similar to the following: 

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md#reference_1A3E7E0CEF6A4D8D801BC363A3C30C1A). 
