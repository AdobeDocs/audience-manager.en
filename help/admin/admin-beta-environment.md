---
description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta Environment
uuid: 6a253f4e-96e7-4395-a783-a8eb213b7daf
---

# Beta Environment{#beta-environment}

The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.

## Overview {#section_519B661403C74F69A3D2E5A5171331FF}

<!-- 

beta_environment_admin.xml

 -->

|Service|URL/Hostname|Steps to Provision|
|--- |--- |--- |
|S3||See [Provision Amazon S3 Buckets](admin-beta-environment.md#section_59499FFC55834D50B9A9105B405BAC9D).|
|DCS|`https://dcs-beta.demdex.net/...`|No extra steps needed from our side. See [Access the DCS in the Beta Environment](admin-beta-environment.md#section_89A9CAB8A0784BF5A7DBA1C8F596CB82).|
|UI|`https://bank-beta.demdex.com`|Data is copied from the production to the beta environment on a monthly basis. Production credentials are valid for beta.|
|API|`https://api-beta.demdex.com/...`|Data is copied from the production to the beta environment on a monthly basis. Production credentials are valid for beta.|

## Provision Amazon S3 Buckets {#section_59499FFC55834D50B9A9105B405BAC9D}

**We are moving away from using FTP/SFTP. Also, please note that Outbound data transfers do not work for the beta environment. To provision S3 buckets for inbound data:**

1. Use the [**SKMS Request TechOps Help**](https://skms.adobe.com/) feature. 
2. Go to **[!UICONTROL Request TechOps Help]** in the left navigation rail. 
3. In **[!UICONTROL Request Search]**, type in Audience Manager in the search field. 
4. Scroll down in the search results and click into **Audience Manager - S3 Inbound / Outbound Account Provisioning**. 
5. Fill in the fields in the provisioning window and specify **Sandbox environment** in the **[!UICONTROL Environment]** field.

>[!NOTE]
>
>Note that we discourage the use of FTP / SFTP and encourage the use of [!UICONTROL Amazon S3]. The reasons why we encourage the use of [!UICONTROL Amazon S3] are listed in [Amazon S3:About](https://marketing.adobe.com/resources/help/en_US/aam/c_as3.html).

## Access the DCS in the Beta Environment {#section_89A9CAB8A0784BF5A7DBA1C8F596CB82}

**To access the [!UICONTROL DCS] in the beta environment:**

1. Make a DCS call, using the curl [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

For example:

`curl -v https://dcs-beta.demdex.net/event`

1. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

For example:

```
curl -v http://dcs-beta.demdex.net/?event
[...]
< DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
[...]
```

<!--
1. Determine the load balancer's endpoint IP addresses.

   Run the `dig` [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the Audience Manager [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

1. Using one of the addresses in the above table, add a static DNS entry in the [!DNL `/etc/hosts`] file.

   On Windows, modify [!DNL `c:\WINDOWS\system32\drivers\etc\hosts`].

   For example:

[!DNL `52.87.15.51 samplepartner.demdex.net`]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

[!DNL `52.87.15.51 dpm.demdex.net`] [!DNL]. 

1. Make a [!UICONTROL DCS] call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

[!DNL `https://<domain>/event?product=camera`] 

1. Verify that your request was served by the beta [!UICONTROL DCS] by looking for "sandbox" in the [!UICONTROL DCS] response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```
-->