---
description: Prerequisites, downloads, available operations, and authentication requirements.
keywords: baaam;BAAAM
seo-description: Prerequisites, downloads, available operations, and authentication requirements.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: Getting Started With Bulk Management
uuid: bc9fafca-e65f-4748-b076-6b24f7d5ed21
index: y
internal: n
snippet: y
translate: y
---

# Getting Started With Bulk Management


>[!NOTE] {type="attention"}
>
>The [!UICONTROL  Bulk Management Tools]* are not* supported by [!DNL  Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [ Audience Manager APIs](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_api.html) instead. [ RBAC group permissions](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296) assigned in the Audience Manager UI are honored in the Bulk Management Tools. 



## Prerequisites {#section_856E85FA4A3145009FD71DA2EF8E17D9}

To use the [!DNL  Bulk Management Tools], you need the following: 

* Your [!DNL  Audience Manager] user name and password. As a customer, you should already have these credentials.
* An API client ID and secret key. Your account manager can provide you with these.
* The [!UICONTROL  Bulk Management Tools] worksheet. **[ Download the worksheet](https://marketing.adobe.com/resources/help/en_US/aam/downloads/BAAAM_August_2018.xlsm)** to get the latest verison.
* Excel running on [!DNL  Windows] or in a [!DNL  Windows] virtual machine running on [!DNL  OS X]. 32-bit Windows is preferred.

## Actions and operations {#section_A4E146C4ADB44AFAA049C048E07240A0}

The [!UICONTROL  Bulk Management Tools] worksheet consists of action tabs, action buttons, and a Headers tab. The Headers tab contains the pre-formatted column headers used by the action tabs. The action tabs contain macros that perform your selected bulk operation. To perform a bulk operation, you copy a set of headers into the appropriate action tab, enter header data, and click an action button. 

Open the spreadsheet and click an action button to get started. 

![](assets/bamwrkbk.png) 

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL  Bulk Management Tools] worksheets. 



<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Actions </th> 
   <th colname="col2" class="entry"> Objects </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bulk actions appear in tabs at the bottom of the worksheet and include: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Requests </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Update </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Create </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimate </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Delete </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <span class="uicontrol"> Headers</span> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../c_features/c_datasources/c_datasources.md#concept_DC7CC030739C436C947078C7877C15AD" format="dita" scope="local"> Data sources</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../c_features/c_tb_derived_signal/c_tb_derived_signal.md#concept_36FF7303F39E4748AC048D08F9E371C6" format="dita" scope="local"> Derived signals</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../c_features/c_destinations/c_destinations.md#concept_5BDA346C376C4B719EA394108AB2735A" format="dita" scope="local"> Destinations</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../c_features/c_tb_overview/c_tb_storage/c_tb_storage.md#concept_492988EC858545AAA5D1B8F06D273BDD" format="dita" scope="local"> Trait folders</a> and segment folders </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../c_features/c_segments/c_segments.md#concept_2044B3AC34AC46669EE7D9292380BE0C" format="dita" scope="local"> Segments</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../c_features/c_tb_overview/c_tb_overview.md#concept_422CE72B2125457B8C2954BF06102332" format="dita" scope="local"> Traits</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Bulk operation example** 

As an example, let's take a look at how to create multiple traits at one time. To create multiple traits in a bulk operation you would: 

1. Click the **[!UICONTROL  Headers]** tab and copy all the labels under the [!UICONTROL  Create a Trait] option.
1. Click the **[!UICONTROL  Create]** tab and paste the labels starting in row 1, column A.
1. Provide information related to each column header and click **[!UICONTROL  Create Traits]**. This action prompts you to log on. Your bulk job runs after you successfully authenticate (see the [ authentication requirements](../../c_reference/c_bulk/c_bulk_start.md#section_6FE9BADB30254A4FADC77D2DCFB6A1EE) below). Check the lower left corner of the worksheet for a job status notification.

>[!NOTE]
>
>When working with large requests, the worksheet might become unresponsive and appear to be inactive. In these cases, just leave it alone. The worksheet will become responsive when the bulk request is complete. If the worksheet does not respond for a long period of time, see the[ troubleshooting section](../../c_reference/c_bulk/r_bulk_troubleshoot.md#reference_1A3E7E0CEF6A4D8D801BC363A3C30C1A). 



## Authentication requirements and options {#section_6FE9BADB30254A4FADC77D2DCFB6A1EE}

Bulk changes require authentication. When you select an action, the worksheet prompts you to log in. Because the worksheet makes API calls, you need to configure it to read your secret key. And, the **[!UICONTROL  Domain]** field lets you make bulk changes in a staging/test environment or against your live, production account. 

![](assets/bamauth.png) 

**API authentication requirements** 

To set up API authentication, you must: 

* Copy and save the secret key to a text (.txt) file.
* Name the text file with your API client ID. For example, if your client ID is "Bulk-User," save the key in a file titled "Bulk-User.txt."
* Save the secret key and worksheet together in the same folder.
When making bulk changes, you'll still have to enter a user name, password, client ID, and domain, but API authentication is automatic. 

**Domain authentication options** 

Domain authentication gives you the option to test bulk requests or apply them directly to your production account. Making bulk changes to the test environment won't affect your production account. Production changes are effective immediately. The **[!UICONTROL  Domain]** field accepts the following addresses, depending on the environment you want to work in: 

* Testing:
* Production:
>[!MORE_LIKE_THIS]
>
>* [  ](https://marketing.adobe.com/resources/help/en_US/aam/downloads/BaaamV4_2.xlsm)
