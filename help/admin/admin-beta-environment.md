---
description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta Environment
uuid: 6a253f4e-96e7-4395-a783-a8eb213b7daf
index: y
internal: n
snippet: y
---

# Beta Environment{#beta-environment}

The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.

## Overview {#section_519B661403C74F69A3D2E5A5171331FF}

<!-- 

beta_environment_admin.xml

 -->

<table id="table_6F388D1F7EC74D859D32ACAB56788412"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Service </th> 
   <th colname="col2" class="entry"> URL/Hostname </th> 
   <th colname="col3" class="entry"> Steps to Provision </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> FTP </td> 
   <td colname="col2"> <span class="filepath"> sandbox-ftp-in.demdex.com</span> </td> 
   <td colname="col3"> <p>See <a href="admin-beta-environment.md#section_59499FFC55834D50B9A9105B405BAC9D" format="dita" scope="local"> Provision Amazon S3 Buckets and FTP / SFTP for Inbound and Outbound Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> DCS </span> </td> 
   <td colname="col2"> <span class="filepath"> https://dcs-beta.demdex.net/...</span> </td> 
   <td colname="col3"> <p>No extra steps needed from our side. See <a href="admin-beta-environment.md#section_89A9CAB8A0784BF5A7DBA1C8F596CB82" format="dita" scope="local"> Access the DCS in the Beta Environment</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UI </td> 
   <td colname="col2"> <span class="filepath"> https://bank-beta.demdex.com </span> </td> 
   <td colname="col3"> <p>Data is copied from the production to the beta environment on a monthly basis. Production credentials are valid for beta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> API </td> 
   <td colname="col2"> <span class="filepath"> https://api-beta.demdex.com/...</span> </td> 
   <td colname="col3"> <p>Data is copied from the production to the beta environment on a monthly basis. Production credentials are valid for beta. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The FTP is used for both inbound and outbound traffic, there is no dedicated FTP for outbound data.

## Provision Amazon S3 Buckets and FTP / SFTP for Inbound and Outbound Data {#section_59499FFC55834D50B9A9105B405BAC9D}

**To provision FTP / SFTP accounts and S3 bucket for inbound/outbound data:**

1. Use the [**SKMS Request TechOps Help**](https://skms.adobe.com/) feature. 
1. Go to **[!UICONTROL Request TechOps Help]** in the left navigation rail. 
1. In **[!UICONTROL Request Search]**, type in Audience Manager in the search field. 
1. Scroll down in the search results and click into **Audience Manager - S3 Inbound / Outbound Account Provisioning**. 
1. Fill in the fields in the provisioning window and specify **Sandbox environment** in the **[!UICONTROL Environment]** field.

>[!NOTE]
>
>Note that we discourage the use of FTP / SFTP and encourage the use of [!UICONTROL Amazon S3]. The reasons why we encourage the use of [!UICONTROL Amazon S3] are listed in [Amazon S3:About](https://marketing.adobe.com/resources/help/en_US/aam/c_as3.html).

## Access the DCS in the Beta Environment {#section_89A9CAB8A0784BF5A7DBA1C8F596CB82}

**To access the [!UICONTROL DCS] in the beta environment:**

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig` [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the Audience Manager [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

1. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

[!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

[!DNL 52.87.15.51 dpm.demdex.net] [!DNL]. 

1. Make a [!UICONTROL DCS] call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

[!DNL https://<domain>/event?product=camera] 

1. Verify that your request was served by the beta [!UICONTROL DCS] by looking for "sandbox" in the [!UICONTROL DCS] response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

