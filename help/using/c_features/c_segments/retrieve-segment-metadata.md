---
description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Retrieving Segment Metadata
uuid: 1df56601-0cda-44e5-948e-fa7ad50628ce
index: y
internal: n
snippet: y
translate: y
---

# Retrieving Segment Metadata

When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.

## Manual method {#section_FC3DBF37844B4A6C8D3E933DA81AACE9}

As a data partner, you're probably used to getting audience metadata from your customers through manual processes. This could include files attached to emails or from customers adding that data through a UI you've built and maintained for this purpose. These processes work, but they're often cumbersome, time consuming, and may require manual data entry work. These methods are often used to help get an integration up and running quickly, but they do not provide the best customer experience in the long run. As an alternative, you can use the [!DNL Audience Manager] API to get segment metadata automatically.

## Automated method {#section_286D2B80BD034D06A26CD88FDD2B232B}

[!DNL Audience Manager] provides a set of [REST APIs](../../c_api/c_rest_api_main/c_rest_api_main.md#concept_B512E6C3410A4304A672588A60A792B1) that let you retrieve segment metadata automatically. With the API, you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. See the steps below for more information.

**Step 1: Review the [!DNL Audience Manager] APIs**

The [Getting Started with REST APIs](../../c_api/c_rest_api_main/aam-api-getting-started.md#concept_2745BC64D5BD43A49DA6020E42280863) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven't worked with the [!DNL Audience Manager] API before.

**Step 2: Request OAuth2 access credentials**

You need a client ID and secret to make API calls. You can obtain a client ID and secret from your integration specialist during the integration set up process. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at amsupport@adobe.com.

**Step 3: Collect customer-specific information from each integrated customer**

Request the following from each integrated customer:

* Username: This is for a restricted user that has read-only permissions for the destination associated with a specific integration. 
* Password: The user password. 
* Destination ID: This is the ID (an integer) associated with the destination created for the specific server-to-server integration.

**Step 4: Retrieve segment metadata with an API call**

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../c_api/c_rest_api_main/aam-api-destinations/aam-api-retrieve-destinations.md#reference_2EF17D608D804F2FAC95AE18B3F0DCA3). This call returns segment data formatted as key-value pairs in a JSON object. Some of the important segment attributes returned in the response are listed in the following table.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager</span> segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> elementName</span> </p> </td> 
   <td colname="col2"> <p>The segment name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> elementDescription</span> </p> </td> 
   <td colname="col2"> <p>Some text that briefly describes the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> elementStatus</span> </p> </td> 
   <td colname="col2"> <p>The current status of the segment mapping. Returned status options include: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <span class="codeph"> active</span> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <span class="codeph"> inactive</span> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <span class="codeph"> deleted</span> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<!-- placeholder to insert space -->

