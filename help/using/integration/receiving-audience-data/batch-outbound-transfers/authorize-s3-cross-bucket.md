---
description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
---
# Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

The [!UICONTROL Outbound Data Transfer] process for customers using [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requires us to ask for your [!DNL Amazon S3] access key and secret key, in order to deliver the outbound data files to your bucket.

If you'd rather not share your [!DNL Amazon S3] access key and secret key with us, contact your [!DNL Audience Manager] consultant or Customer Care and they will set up [!DNL Cross-Account Bucket Permissions] for you.

You only need to add our [!DNL Amazon S3] account ID to an allow list for the [!DNL S3] bucket where you wish to receive the outbound data files, as described in the [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Your [!DNL Audience Manager] consultant or Customer Care will provide you with our [!DNL Amazon S3] account ID.

>[!NOTE]
>
>Due to the Amazon S3 object size limit, Audience Manager supports split sizes of up to 1 TB. If you do not specify any split size, the 1 TB limit is automatically applied.

