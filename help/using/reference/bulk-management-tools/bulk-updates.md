---
description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Bulk Updates
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
TQID: https://experienceleague.adobe.com/fDSvlPqWTgaw-SszCIa5M2qxJcyfrewPaW03eVShhDw
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
    internal-label: REST APIs
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Bulk Updates{#bulk-updates}

A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.

>[!IMPORTANT]
>
>The Bulk Management Tools are not an officially supported Adobe offering. Troubleshooting and support through Customer Care will be handled on a case by case basis.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and: 

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
2. Click the **[!UICONTROL Update]** tab.
3. Paste the update headers into the first row of the update worksheet. Note the following:

    * When updating a folder, all headers are required. 
    * When updating segments or traits, you only need the segment ID (SID) and the header element that needs to be changed. Delete unused headers.

4. Paste or type the data you want to change into a corresponding column based on the header label.
5. In the worksheet toolbar, click an update button that matches the        item you're updating.
   This action opens the [!UICONTROL Account Information] dialog box. 

6. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Before entering data, your bulk update worksheet should look similar to the following: 

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
