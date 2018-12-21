---
description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: Customer Data Feed FAQ
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
---

# Customer Data Feed FAQ{#customer-data-feed-faq}

Frequently asked questions about Customer Data Feed (CDF) files.

## Amazon S3 Storage {#section_1FBC4A7E4166488BAA9C74E8A8BB73C3}

**Where is my CDF file stored on [!DNL Amazon]?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../c-features/cdf-files.md#reference_DAC53BEEA60B426588D1B66B3B92E8C1).

**Is my storage bucket secure?**

Yes. Customers get access to their own storage space only. You will have read-only access to your storage bucket. You will not have write access.

**Can I customize my storage bucket or store files in another directory?**

No. Customization and alternate storage options are not available.

**My directory is missing a file for particular hour. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. This usually happens when our servers get behind in processing CDF files. In this case, your file is not lost. It will appear in a later hourly directory after our system has a chance to catch up. See also, [Customer Data Feed File Processing Notifications](../c-features/cdf-files.md#concept_00F913A9946A4A10A0F34269AC84A563).

**How do I know when my CDF files are ready?**

See [Customer Data Feed File Processing Notifications](../c-features/cdf-files.md#concept_00F913A9946A4A10A0F34269AC84A563).

## File Sizes {#section_3469175E380844559B95B78BB4727D4E}

**What sort of file sizes should I expect? How big is an average CDF file?**

It is difficult to estimate file sizes. And, each file can be a different size. Sizes will vary from hour to hour and day to day. If you're going to receive CDF files, it helps to be prepared to manage a lot of data.

**How many files will I receive?**

Again, it is difficult to estimate this. However, if you're going to receive CDF files it helps to be prepared to manage a lot of data.

## Data Integrity {#section_588180928BB044F5A556638EFF875453}

**How can I check the integrity of the data uploaded to Amazon S3?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] generates an `ETag` value for multi-part uploads. It first calculates the individual MD5 checksums of each uploaded part, then concatenates them into a single string. Then, it calculates the MD5 checksum of the string. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

## Data Retention {#section_CCC63714F3E046C6A4C8FF8D0AAA88BD}

**How long do you store CDF files?**

Data is deleted after 8 days.

**Can I get CDF files retroactively or for previous days?**

You can only generate CDF files for the past 8 days. CDF files for intervals older than the past 8 days cannot be re-generated. 

>[!MORE_LIKE_THIS]
>
>* [Customer Data Feeds](../c-features/cdf-files.md#concept_114B993EC5E246AE8CDD55E695B344FC)
