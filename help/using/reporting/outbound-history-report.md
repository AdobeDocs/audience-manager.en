---
description: View outbound batch job history information for a specified destination and time period.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Outbound File History
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: inbound and outbound reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
---
# Outbound File History {#outbound-file-history}

View outbound batch job history information for a specified destination and time period.

<!-- 

t_reports_outbound_history.xml

 -->

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Step Result](assets/outbound_history.png)

1. In the **[!UICONTROL Search for a Destination]** box, start typing and select the desired destination.
1. In the **[!UICONTROL Select a Date Range]** box, specify the start and end dates for your report, then click **[!UICONTROL Apply Date Filter]**.

   ![Step Result](assets/outbound_history_stats.png)

   The following table contains information corresponding to columns in the report:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Line </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Sync File Name </td> 
   <td colname="col2"> <p>List of all outbound files that <span class="keyword"> Adobe</span> generated for this destination that were processed together. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Successful </td> 
   <td colname="col2"> <p>Number of records that were successfully sent from <span class="keyword"> Audience Manager</span> to the destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Failed </td> 
   <td colname="col2"> <p>Number of records that could not be sent to the destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Records Received </td> 
   <td colname="col2"> <p>Total number of records <span class="keyword"> Adobe</span> generated in the files and attempted to send to the destination. In most cases, this should be the total number of successful files and failed files. </p> </td> 
  </tr> 
 </tbody> 
</table>
