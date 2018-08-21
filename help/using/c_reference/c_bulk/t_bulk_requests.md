---
description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Bulk Requests
uuid: cd74693e-ed3a-48a9-a6f3-ca00541ff64d
index: y
internal: n
snippet: y
translate: y
---

# Bulk Requests


>[!NOTE] {type="attention"}
>
>The [!UICONTROL  Bulk Management Tools]* are not* supported by [!DNL  Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [ Audience Manager APIs](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_api.html) instead. [ RBAC group permissions](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296) assigned in the Audience Manager UI are honored in the Bulk Management Tools. 



The [!UICONTROL  Request] worksheet does not have its own set of column headers and you don't need to copy IDs to any of the columns. Instead, it returns data based on the action button you click in the toolbar. And, an optional reporting feature returns a frequency count for pixel fires and unique user count for several fixed time intervals. 

To make bulk requests, open the [!UICONTROL  Bulk Management Tools] worksheet and: 

>1. Click the **[!UICONTROL  Request]** tab.
>1. In the tool bar at the top of the worksheet, click a request button corresponding to the data you want to work with. You can request:
>    * Data provider IDs
>    * Derived signals
>    * Destination mappings
>    * Rule-based and on-boarded traits
>    * Segments
>    * Trait and segment folder IDs

>       The [!DNL  Audience Manager] API writes bulk data back to the [!UICONTROL  Request] worksheet. 

>>[!NOTE]
>>
>>In your results, the ` createTime` and ` updateTime` columns return data in exponential notation. The underlying date/time stamps are recorded in UNIX UTC time. Currently, the worksheet cannot return date/time stamps in a readable format. 
>
>If your bulk update returns an error or fails, see [ Troubleshooting for Bulk Management Tools](../../c_reference/c_bulk/r_bulk_troubleshoot.md#reference_1A3E7E0CEF6A4D8D801BC363A3C30C1A). 

