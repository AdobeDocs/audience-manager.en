---
description: A bulk update lets you edit multiple segments, traits, and segment or trait folders elements in a single operation. Follow these instructions to make bulk updates.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, and segment or trait folders elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Bulk Updates
uuid: 96885617-9963-413e-b769-94bf2c72bc7c
index: y
internal: n
snippet: y
translate: y
---

# Bulk Updates

A bulk update lets you edit multiple segments, traits, and segment or trait folders elements in a single operation. Follow these instructions to make bulk updates.




>[!NOTE] {type="attention"}
>
>The [!UICONTROL Bulk Management Tools]* are not* supported by [!DNL Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [Audience Manager APIs](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_api.html) instead. [RBAC group permissions](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296) assigned in the Audience Manager UI are honored in the Bulk Management Tools. 



To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and: 

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Paste the update headers into the first row of the update worksheet. Note the following:

    * When updating a folder, all headers are required.    
    * When updating segments or traits, you only need the segment ID (SID) and the header element that needs to be changed. Delete unused headers.    
    
    
1. Paste or type the data you want to change into a corresponding column based on the header label.
1. In the worksheet toolbar, click an update button that matches the item you're updating.

[!UICONTROL Account Information]1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#section_6FE9BADB30254A4FADC77D2DCFB6A1EE) and click **[!UICONTROL Submit]**.

[!UICONTROL Results][!UICONTROL Results][REST APIs](../../c_api/c_rest_api_main/c_rest_api_main.md#concept_B512E6C3410A4304A672588A60A792B1)>
>
>Before entering data, your bulk update worksheet should look similar to the following: >
>
>![](assets/update.png) 
>
>
>If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md#reference_1A3E7E0CEF6A4D8D801BC363A3C30C1A). 

