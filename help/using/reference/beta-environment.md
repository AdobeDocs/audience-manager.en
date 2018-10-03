---
description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta Environment
uuid: 933c05cc-199e-44f3-ad7c-cd151034d52a
index: y
internal: n
snippet: y
translate: y
---

# Beta Environment

The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.



**Update Schedule** 


The beta environment is updated at the end of each month during off-peak hours. 



<!-- Added re: AAM-30826. -->



**Endpoints** 

<table id="table_6F388D1F7EC74D859D32ACAB56788412"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Service </th> 
   <th colname="col2" class="entry"> URL/Hostname </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>FTP </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> sandbox-ftp-in.demdex.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DCS </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> https://dcs-beta.demdex.net/...</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UI </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> https://bank-beta.demdex.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> https://api-beta.demdex.com/...</span> </p> </td> 
  </tr> 
 </tbody> 
</table>




>[!NOTE]
>
>The FTP is used for both inbound and outbound traffic, there is no dedicated FTP for outbound data.



**To access the DCS in the beta environment:** 

1. 

   Determine the load balancer's endpoint IP addresses. 


   Run the `dig` [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)]. 

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

1. 

   Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file. 


   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts]. 


   For example: 


[!DNL 52.87.15.51 *`samplepartner`*.demdex.net] 



   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date. 



   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.] 


[!DNL 52.87.15.51 dpm.demdex.net] [!DNL]. 

1. 

   Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols. 


   For example: 


[!DNL https://<domain>/event?product=camera] 

1. 

   Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header. 


   For example: 


   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```




