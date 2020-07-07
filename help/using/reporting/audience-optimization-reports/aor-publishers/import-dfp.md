---
description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Import Google Ad Manager Data Files Into Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: audience optimization reports
---

# Import Google Ad Manager (formerly DFP) Data Files Into Audience Manager{#import-dfp-data-files-into-audience-manager}

Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.

## Prerequisites for Google Ad Manager Log Ingestion {#prereqs-dfp-ingestion}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement.

In order to use [!DNL Google Ad Manager] (formerly Google DFP) log files in [!DNL Audience Manager], you must first set our [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) in the ad tag call. By doing this, our ID is included in the [!DNL Google Ad Manager] logs and we can match IDs between [!DNL Google Ad Manager] and [!DNL Audience Manager]. Use [!DNL Audience Manager] [!UICONTROL DIL] code or the [!UICONTROL Audience Management Module] to set the [!DNL Audience Manager] UUID in a first party cookie.

Here is how to set the [!DNL Audience Manager] ID in the ad tag call, as explained in our documentation:

* [Via Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md) 
* [Via a Cookie Destination](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

You need to set the [!DNL Audience Manager] ID yourself, and can work with [!DNL Audience Manager] consulting to check if everything works. You have set the [!DNL Audience Manager] ID correctly if:

* `'aamid'` is the key used as the identifier. 
* The User ID value is correctly formatted as the [!DNL Audience Manager] UUID, as described in our [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md). 
* You have included the [!DNL Audience Manager] UUID in a defined field in your [!DNL Google Ad Manager] logs (e.g. CustomTargeting).

## Prerequisites for Log Ingestion Enablement {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Step </th> 
   <th colname="col2" class="entry"> Details </th> 
   <th colname="col3" class="entry"> Owner </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Step 1 </p> </td> 
   <td colname="col2"> <p>Confirm that the required steps to set the <span class="keyword"> Audience Manager</span> UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Customer Care or Consulting </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 2 </p> </td> 
   <td colname="col2"> <p>Your Google Ad Manager Administrator creates: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting Google Ad Manager logs into <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">New credentials. <p>Note:  This may require a unique e-mail address specific to this project and will be used when provisioning access to the Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">A Private key (JSON based credential) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Your Google Ad Manager Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 3 </p> </td> 
   <td colname="col2"> <p>Your Google Ad Manager Administrator grants API access to the service account. This step enables access to the metadata to delineate dimensions (line items, orders, creatives). <p>Note:  Use the service account e-mail access that you set up in step 2 to grant permission to access the API. </p> </p> </td> 
   <td colname="col3"> <p>Your Google Ad Manager Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 4 </p> </td> 
   <td colname="col2"> <p>Your Google Ad Manager Administrator establishes access to the Google Storage Bucket. Remember: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">This can be done via a Google group. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associate the unique email address assigned to the service account to the storage bucket. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Your Google Ad Manager Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 5 </p> </td> 
   <td colname="col2"> <p>Your Google Ad Manager Administrator provides the Google Ad Manager Network ID. This allows us to pass in the Network ID when making calls to the API. </p> </td> 
   <td colname="col3"> <p>Your Google Ad Manager Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 6 </p> </td> 
   <td colname="col2"> <p>Compile the pre-requisites in an e-mail to AAM Customer Care (aamsupport@adobe.com) to kick off the log ingestion process. Draft the e-mail using the template in the next section. </p> </td> 
   <td colname="col3"> <p>You, or <span class="keyword"> Audience Manager</span> Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail Template {#email-template}

To finalize the log ingestion enablement, send us an e-mail to aamsupport@adobe.com. Please use the [attached e-mail template](assets/enable_dfp_ingestion.txt).
