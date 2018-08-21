---
description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import DFP Data Files Into Audience Manager
solution: Audience Manager
title: Import DFP Data Files Into Audience Manager
uuid: f7d7b693-646b-44fe-9c7f-e0fc9b3678cb
index: y
internal: n
snippet: y
translate: y
---

# Import DFP Data Files Into Audience Manager

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../../../c_features/c_analytics/audience-optimization-reports/aor-publishers/import-dfp.md#section_BCF5B581A7234CEE8DC9D4F578D34EDF" format="dita" scope="local"> Prerequisites for DFP Log Ingestion </a> </li> 
 <li> <a href="../../../../c_features/c_analytics/audience-optimization-reports/aor-publishers/import-dfp.md#section_C9F2432E46B04C89B52752825650DADE" format="dita" scope="local"> Prerequisites for Log Ingestion Enablement </a> </li> 
 <li> <a href="../../../../c_features/c_analytics/audience-optimization-reports/aor-publishers/import-dfp.md#section_36708E8B91C84BB19E7FC5C6B9B81428" format="dita" scope="local"> E-Mail Template </a> </li> 
</ul>



## Prerequisites for DFP Log Ingestion {#section_BCF5B581A7234CEE8DC9D4F578D34EDF}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement. 

In order to use DFP (DoubleClick For Publishers) log files in Audience Manager, you must first set our [ Audience Manager Unique User ID (UUID)](../../../../c_reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8) in the ad tag call. By doing this, our ID is included in the DFP logs and we can match IDs between DFP and Audience Manager. Use Audience Manager DIL code or the Audience Management Module to set the Audience Manager UUID in a first party cookie. 

Here is how to set the Audience Manager ID in the ad tag call, as explained in our documentation: 


* [ Via Google Publisher Tag (GPT)](../../../../c_integration/gpt-aam-destination/gpt-aam-create-destination.md#concept_CD39E47404A541719119E9F354EB274C)
* [ Via a Cookie Destination](../../../../c_integration/gpt-aam-destination/gpt-aam-modify-api.md#concept_276DF2F702BE4D6180C855A7DE304097)


You need to set the Audience Manager ID yourself, and can work with Audience Manager consulting to check if everything works. You have set the Audience Manager ID correctly if: 


* ` 'aamid'` is the key used as the identifier. 

* The User ID value is correctly formatted as the Audience Manager UUID, as described in our [ Index of IDs in Audience Manager](../../../../c_reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8). 

* You have included the Audience Manager UUID in a defined field in your DFP logs (e.g. CustomTargeting). 



## Prerequisites for Log Ingestion Enablement {#section_C9F2432E46B04C89B52752825650DADE}



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
   <td colname="col2"> <p>Confirm that the required steps to set the Audience Manager UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p>Audience Manager Customer Care or Consulting </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 2 </p> </td> 
   <td colname="col2"> <p>Your DFP Administrator creates: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting DFP logs into Audience Manager. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">New credentials. <p>Note:  This may require a unique e-mail address specific to this project and will be used when provisioning access to the Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">A Private key (JSON based credential) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Your DFP Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 3 </p> </td> 
   <td colname="col2"> <p>Your DFP Administrator grants API access to the service account. This step enables access to the metadata to delineate dimensions (line items, orders, creatives). <p>Note:  Use the service account e-mail access that you set up in step 2 to grant permission to access the API. </p> </p> </td> 
   <td colname="col3"> <p>Your DFP Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 4 </p> </td> 
   <td colname="col2"> <p>Your DFP Administrator establishes access to the Google Storage Bucket. Remember: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">This can be done via a Google group. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associate the unique email address assigned to the service account to the storage bucket. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Your DFP Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 5 </p> </td> 
   <td colname="col2"> <p>Your DFP Administrator provides the DFP Network ID. This allows us to pass in the Network ID when making calls to the API. </p> </td> 
   <td colname="col3"> <p>Your DFP Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 6 </p> </td> 
   <td colname="col2"> <p>Compile the pre-requisites in an e-mail to AAM Customer Care (aamsupport@adobe.com) to kick off the log ingestion process. Draft the e-mail using the template in the next section. </p> </td> 
   <td colname="col3"> <p>You, or Audience Manager Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>


## E-Mail Template {#section_36708E8B91C84BB19E7FC5C6B9B81428}

To finalize the log ingestion enablement, send us an e-mail to aamsupport@adobe.com. Please use the [ attached e-mail template](https://marketing.adobe.com/resources/help/en_US/aam/downloads/enable_dfp_ingestion.txt). 
