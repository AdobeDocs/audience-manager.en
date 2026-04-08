---
description: To send data from your own Amazon S3 bucket to Audience Manager, you must first request the configuration of a dedicated Amazon S3 role.
solution: Audience Manager
title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Inbound Files
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
TQID: https://experienceleague.adobe.com/DR-nafoDKl-1VPK2xwq-iqpwkuTYk2nN3ywOycVJ3jM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Leverage Amazon S3 Cross-Account Bucket Permissions for Your Inbound Files {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

To send data from your own Amazon S3 bucket to Audience Manager, you must first request the configuration of a dedicated Amazon S3 role.

To do this, follow the steps outlined below.

1. Contact Customer Care and request an alternative method of sending files to Audience Manager.
2. Provide Customer Care with the [!DNL Amazon Resource Name (ARN)] for a role in your Amazon S3 account that you will be using to send files. _This role must be created before you contact Customer Care_. After the configuration is complete, Customer Care will provide you the [!DNL Amazon Resource Name (ARN)] for the newly created role.
3. Edit the permissions of your existing Amazon S3 role to assume the role provided by Customer Care.

>[!NOTE]
>
>When transfering inbound data to the Audience Manager Amazon S3 bucket, make sure to use the `bucket-owner-full-control` [access control list](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) in order for Audience Manger to correctly process the data.
>
>Example for the Amazon Web Services command: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
