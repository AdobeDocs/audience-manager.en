---
description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta Environment
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
---
# Beta Environment {#beta-environment}

The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.

## Overview

The beta environment is an exact replica of the production environment, without any experimental or unreleased features. Your login credentials from the production environment are valid in the beta environment.

**Update Schedule**

The beta environment is updated at the end of each month during off-peak hours.

**Outbound Traffic**

Outbound traffic is not enabled for the beta environment.

<!-- 

Added re: AAM-30826.

 -->

## Endpoints



| Service | URL/Hostname | How to obtain access |
|--- |--- | --- |
|S3|Contact your Audience Manager Partner Solutions representative or Customer Care| Contact your Audience Manager Partner Solutions representative or Customer Care to set up an Amazon S3 bucket for your beta instance. Read about the [advantages of using Amazon S3](../reference/amazon-s3.md). |
|DCS|`https://dcs-beta.demdex.net/...`| See [Accessing the DCS in the Beta Environment](../reference/beta-environment.md#access-dcs-beta-environment). |
|UI|`https://bank-beta.demdex.com`| Your production environment credentials are valid for the beta environment. |
|API|`https://api-beta.demdex.com/...`| Your production environment credentials are valid for the beta environment. We recommend that you create a generic API user, [see details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accessing the DCS in the Beta Environment {#access-dcs-beta-environment}

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

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
