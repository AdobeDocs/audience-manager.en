---
description: A reference guide for the labels and terms used in this report.
seo-description: A reference guide for the labels and terms used in this report.
seo-title: Onboarding Status Report Terms and Definitions
solution: Audience Manager
title: Onboarding Status Report Terms and Definitions
uuid: b611a1f0-adda-4e6b-b8f4-191a4a6a528b
index: y
internal: n
snippet: y
translate: y
---

# Onboarding Status Report Terms and Definitions


<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Term </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Data Sync File Name</b> </p> </td> 
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>File processing will fail if the file name is formatted improperly. File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include Amazon S3 and FTP. For instructions on how to name your files, see: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/inbound-s3-filenames.md#concept_B3CAF442BFFE4823B76A5D0D91DF9942" format="dita" scope="local"> Amazon S3 Name Requirements for Inbound Data Files </a> </li> 
      <li id="li_9590241AEC0C482D91C64DB760B32B0D"> <a href="../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/inbound-ftp-filenames.md#concept_D34898442363415DBF75CEBFC2E86997" format="dita" scope="local"> FTP Name Requirements for Inbound Data Files </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Format Errors</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of records that failed processing because they did not match the syntax or formatting requirements. See <a href="../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/inbound-file-contents.md#concept_49E6F0740E794B07ACD115D10EDEB5AC" format="dita" scope="local"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Invalid AAM ID</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). Usually, this indicates the IDs: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Did not match the expected 38-digit format. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contain alphabetical characters. IDs should be numbers only. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>No Matching AAM ID</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. Onboarded IDs can have this status when <span class="keyword"> Audience Manager</span> has not yet performed an ID sync or it still can't match the ID even after a synch. </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continue to store and try to synch this ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a Stored Record in the report if the ID cannot be synched. </li> 
    </ul> <p>If your onboarded file contains mobile IDs, then you can treat these numbers a bit more lightly than the other metrics. They will not affect the success and match rates for subsequent files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>No Trait Realized</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. This could be the result of: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Improperly formatted traits in your inbound data file. For on how to format your data file, see <a href="../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/inbound-file-contents.md#concept_49E6F0740E794B07ACD115D10EDEB5AC" format="dita" scope="local"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Percent Success</b> </p> </td> 
   <td colname="col2"> <p>The percentage of records in your file that were stored successfully. Percent success = records processed / number of records in a file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Records Received</b> </p> </td> 
   <td colname="col2"> <p>The total number of records received. In most cases, this number should match the total number of records (lines) in your inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Stored Records</b> </p> </td> 
   <td colname="col2"> <p>Number of records stored successfully. Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. The number of stored records can be less than the number of records received. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total Realized Traits</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total Unused Signals</b> </p> </td> 
   <td colname="col2"> <p>Total number of unused signals received in the report. This total is based on the total number of successfully stored records. </p> <p>See <a href="../../../c_features/c_analytics/c_dynamic_reports/c_unused_signals.md#concept_D3A6A3AD84AE47589699A13A8F971BE0" format="dita" scope="local"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

