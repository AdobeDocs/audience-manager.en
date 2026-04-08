---
description: Audience Manager sends batch data to third-party content providers according to these specifications.
seo-description: Adobe Audience Manager (AAM) sends batch data to third-party content providers according to these specifications.
seo-title: Batch Outbound Data Transfers in Adobe Audience Manager (AAM)
title: Batch Outbound Data Transfers
feature: Outbound Data Transfers
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
TQID: https://experienceleague.adobe.com/jRSfzxiGp-aHxaHELYDQg33faxtMiNbKmbwXoyFoBeM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Batch Outbound Data Transfers

Audience Manager sends batch data to third-party content providers according to these specifications.

* [Outbound Data File Name: Syntax and Examples](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

  Describes the required fields, syntax, and conventions used to name an outbound data file.

* [Configure Batch Data Transfer Integration](batch-server-configuration.md)

  Describes the methods through which you can get your batch data transfer integration configured.

* [Transfer-Control Files for Log File Transfers](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

  Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

* [Outbound Template Macros](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

  Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.

* [Outbound Macro Examples](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

  Examples of how some of the common macros are used to create outbound file templates.

* [Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

  The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
