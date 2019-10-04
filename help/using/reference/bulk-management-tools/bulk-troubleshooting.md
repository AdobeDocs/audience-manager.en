---
description: What to do when the worksheets return an error or your bulk request fails.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Troubleshooting Tips for Bulk Management Tools
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
---

# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

What to do when the worksheets return an error or your bulk request fails.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

Factors like heavy network traffic, server usage, and large data sets can cause a bulk request to fail or time out. If there is an issue, the worksheet stops writing data and displays an error message. When this happens, you should:

* Read the error message. 
* Fix the problem. 
* Delete all the rows that have been already updated. 
* Try the bulk request again.

## Long delays or unresponsive behavior {#delays-behavior}

The following table lists some common problems you may encounter when making bulk requests with the worksheets. Try to fix these issues with the recommended solutions. If the recommended solutions do not resolve the problem, you should save your work, restart your computer, and try the request again without launching or working with other applications.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problem </th> 
   <th colname="col2" class="entry"> Solution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Long delays</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Turn off compatibility mode</b>: Check if you have other worksheets open in Microsoft Excel's compatibility mode. Compatibility mode can increase runtimes. Close any spreadsheets you may have open in this mode and try your bulk request again. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>System resources</b>: Limited system resources contribute to long delays. Try closing all your other programs before making a bulk request. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>No response</b> </td> 
   <td colname="col2">If you click on an action button and nothing happens: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Make sure you have the right set of headers for the selection action. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Make sure you're using the right worksheet for the copied headers. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Check the position of the data you want to use in a bulk operation. All headers start in column A, row 1. All data goes in corresponding headers starting in column A, row 2 (immediately below the headers). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Error Messages

Sometimes, you can receive error messages when making bulk changes. To interpret the error message, see [Response Codes Defined](/help/using/api/rest-api-main/aam-api-getting-started.md) in our API documentation.

