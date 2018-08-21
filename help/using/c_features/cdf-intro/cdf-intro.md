---
description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Customer Data Feeds
uuid: 0a4deb4f-67d0-441e-b5e5-943e3cc7680b
index: y
internal: n
snippet: y
translate: y
---

# Customer Data Feeds

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../c_features/cdf-intro/cdf-intro.md#section_F0D2FA4C021A4C5EBC1D5308AE2F256F" format="dita" scope="local"> File Contents and Purpose </a> </li> 
 <li> <a href="../../c_features/cdf-intro/cdf-intro.md#section_5DCA2FA476E048A797C1021E5C75AA92" format="dita" scope="local"> Getting Started </a> </li> 
 <li> <a href="../../c_features/cdf-intro/cdf-intro.md#section_AB55E04E26D9464D8EB911D51B45E4B8" format="dita" scope="local"> Next Steps </a> </li> 
</ul>



## File Contents and Purpose {#section_F0D2FA4C021A4C5EBC1D5308AE2F256F}

A CDF file contains the same data that an [!DNL  Audience Manager] event call ( ` /event`) sends to our servers. This includes data like user IDs, trait IDs, segment IDs, and all the other parameters captured by an event call. Internal [!DNL  Audience Manager] systems processes event data into a CDF file with content organized into fields that appear in a set order. [!DNL  Audience Manager] tries to generate CDF files hourly and stores them in a secure, customer-specific bucket on an Amazon S3 server. We provide these files so you can work with [!DNL  Audience Manager] data outside of the limits imposed by our user interface. 


>[!NOTE] {type="attention"}
>
>You should not use CDF files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.



## Getting Started {#section_5DCA2FA476E048A797C1021E5C75AA92}

There is no self-service process to start CDF file delivery. Contact your [!DNL  Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL  Audience Manager] representative will: 


* Set up your Amazon S3 storage bucket.
* Provide read-only S3 authentication credentials to your file storage bucket. You will not be able to see or access directories and files that belong to other customers.


File notifications and CDF files will appear in your S3 bucket when they're ready for download. You're responsible for monitoring and downloading files from your assigned S3 directory. See [ Customer Data Feed File Processing Notifications](../../c_features/cdf-intro/cdf-notifications.md#concept_00F913A9946A4A10A0F34269AC84A563) . 

## Next Steps {#section_AB55E04E26D9464D8EB911D51B45E4B8}

The following documentation and the [ Customer Data Feed FAQ](../../c_aam_faq_intro/cdf-faq.md#concept_E832A7307FA0475C918F95116C21CBC6) can help you become more familiar with this service. 
