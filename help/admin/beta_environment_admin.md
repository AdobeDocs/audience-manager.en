---
description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta Environment
uuid: a9e83d26-794a-41cc-8d32-2773d2db5aa6
index: y
internal: n
snippet: y
translate: y
---

# Beta Environment



|  Service  | URL/Hostname  |
|---|---|
|  FTP  | [!DNL  sandbox-ftp-in.demdex.com]  |
|  DCS  | [!DNL  https://dcs-beta.demdex.net/...]  |
|  UI  | [!DNL  https://bank-beta.demdex.com]  |
|  API  | [!DNL  https://api-beta.demdex.com/...]  |


>[!NOTE]
>
>The FTP is used for both inbound and outbound traffic, there is no dedicated FTP for outbound data.



**To access the DCS in the beta environment:** 

1. Determine the load balancer's endpoint IP addresses. 

   Run the ` dig` [ command ](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The ` dig` command queries the Domain Name System and returns the name and IP addresses of the Audience Manager Data Collection Servers (DCS). 

   ```
   dig dcs-beta.demdex.net 
   ... 
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51 
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8 
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

1. Using one of the addresses in the above table, add a static DNS entry in the [!DNL  /etc/hosts] file. 

   On Windows, modify [!DNL  c:\WINDOWS\system32\drivers\etc\hosts]. 

   For example: 

[!DNL  52.87.15.51 *` samplepartner`*.demdex.net] 


   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL  /etc/hosts] file up to date. 


   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL  dpm.demdex.net.] 

[!DNL  52.87.15.51 dpm.demdex.net] [!DNL]. 

1. Make a DCS call, using the ` curl` [ command ](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols. 

   For example: 

[!DNL  https://<domain>/event?product=camera] 

1. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header. 

   For example: 


   ```
   curl -v http://dcs-beta.demdex.net/?event 
   [...] 
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number> 
   [...]
   ```



>[!NOTE] {importance="high"}
>


