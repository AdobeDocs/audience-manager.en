---
description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: Customer Data Feed FAQ
uuid: 2d5188ff-8439-44f5-a1ae-d979a08c3ffe
index: y
internal: n
snippet: y
translate: y
---

# Customer Data Feed FAQ

Contents: 


<ul class="simplelist"> 
 <li> <a href="../c_aam_faq_intro/cdf-faq.md#section_1FBC4A7E4166488BAA9C74E8A8BB73C3" format="dita" scope="local"> Amazon S3 Storage</a> </li> 
 <li> <a href="../c_aam_faq_intro/cdf-faq.md#section_3469175E380844559B95B78BB4727D4E" format="dita" scope="local"> File Sizes </a> </li> 
 <li> <a href="../c_aam_faq_intro/cdf-faq.md#section_CCC63714F3E046C6A4C8FF8D0AAA88BD" format="dita" scope="local"> Data Retention </a> </li> 
</ul>



## Amazon S3 Storage {#section_1FBC4A7E4166488BAA9C74E8A8BB73C3}

**Where is my CDF file stored on Amazon?** 

Your CDF file is stored in the ` aam-cdf` root directory on an Amazon S3 server. This default bucket is managed by [!DNL  Audience Manager]. See also [ Customer Data Feed File Naming Conventions](../c_features/cdf-intro/cdf-file-name.md#reference_DAC53BEEA60B426588D1B66B3B92E8C1). 

**Is my storage bucket secure?** 

Yes. Customers get access their own storage space only. You will have read-only access to your storage bucket. You will not have write access. 

**Can I customize my storage bucket or store files in another directory?** 

No. Customization and alternate storage options are not available. 

**My directory is missing a file for particular hour. Where is it?** 

A missing file means Audience Manager was not able to process your CDF files for that hour. This usually happens when our servers get behind in processing CDF files. In this case, your file is not lost. It will appear in a later hourly directory after our system has a chance to catch up. See also, [ Customer Data Feed File Processing Notifications](../c_features/cdf-intro/cdf-notifications.md#concept_00F913A9946A4A10A0F34269AC84A563). 

**How do I know when my CDF files are ready?** 

See [ Customer Data Feed File Processing Notifications](../c_features/cdf-intro/cdf-notifications.md#concept_00F913A9946A4A10A0F34269AC84A563). 

## File Sizes {#section_3469175E380844559B95B78BB4727D4E}

**What sort of file sizes should I expect? How big is an average CDF file?** 

It is difficult to estimate file sizes. And, each file can be a different size. Sizes will vary from hour to hour and day to day. If you're going to receive CDF files, it helps to be prepared to manage a lot of data. 

**How many files will I receive?** 

Again, it is difficult to estimate this. However, if you're going to receive CDF files it helps to be prepared to manage a lot of data. 

## Data Retention {#section_CCC63714F3E046C6A4C8FF8D0AAA88BD}

**How long do you store CDF files?** 

Data is deleted after 8 days. 

**Can I get CDF files retroactively or for previous days?** 

You can only generate CDF files for the past 8 days. CDF files for intervals older than the past 8 days cannot be re-generated. 
>[!MORE_LIKE_THIS]
>
>* [ Customer Data Feeds ](cdf-intro.md#concept_114B993EC5E246AE8CDD55E695B344FC)
