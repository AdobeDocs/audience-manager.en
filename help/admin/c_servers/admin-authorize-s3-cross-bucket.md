---
description: Some customers may not want to provide their Amazon Simple Storage Service (Amazon S3) access or secret keys to Adobe to authorize destination data upload to their buckets.
seo-description: Some customers may not want to provide their Amazon Simple Storage Service (Amazon S3) access or secret keys to Adobe to authorize destination data upload to their buckets.
seo-title: How To  Authorize Cross-Account Amazon S3 Bucket Access for Batch Destinations
title: How To  Authorize Cross-Account Amazon S3 Bucket Access for Batch Destinations
uuid: 842057de-5f0c-43fa-a135-154a60807484
index: y
internal: n
snippet: y
translate: y
---

# How To: Authorize Cross-Account Amazon S3 Bucket Access for Batch Destinations

An alternative that we can offer our customers is Cross-Account Bucket Permissions in Amazon S3. This process is described in the [ AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). To enable this alternative in Audience Manager, follow the steps below: 

>1. Go to **[!UICONTROL  Servers]** and select **[!UICONTROL  Create Server]**.
>1. Select **[!UICONTROL  S3]** in the **[!UICONTROL  Protocol/Credentials]** drop-down mask.
>1. Check the **[!UICONTROL  Use Internal Adobe Key]** option.
>1. Use your customer's account and bucket name in Amazon S3.
>1. Make sure that your customer white lists the Amazon S3 account 975822914085 on their S3 bucket.
>Our Outbound publisher ensures that the permission level ` bucket-owner-full-control` is set on uploaded data, so that your customer can own that data. 
