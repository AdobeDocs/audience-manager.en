---
description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Bulk Estimates
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
TQID: https://experienceleague.adobe.com/FDD4gSg00I8p4sRqxE9sEpO5dSkGEXpH3hUD6h5CAtI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
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
# Bulk Estimates{#bulk-estimates}

A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.

>[!IMPORTANT]
>
>The Bulk Management Tools are not an officially supported Adobe offering. Troubleshooting and support through Customer Care will be handled on a case by case basis.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and: 

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
2. Click the **[!UICONTROL Estimate]** tab.
3. Paste the estimate header into the first row of the estimate worksheet.
4. Paste or type the data you want to change into a corresponding column based on the header label.
5. In the worksheet toolbar, click the create button that matches the item you're updating.
This action opens the [!UICONTROL Account Information] dialog box. 
6. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. Before entering data, your bulk estimate worksheet should look similar to the following: 

![](assets/estimate.png)
If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
