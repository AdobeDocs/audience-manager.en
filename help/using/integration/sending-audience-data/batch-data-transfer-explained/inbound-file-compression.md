---
description: As an option, you can compress data files when sending them to Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: File Compression for Inbound Data Transfer Files
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
---
# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

You can compress data files when sending them to Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip (`.gz`) compression for inbound, asynchronous data transfers.

Audience Manager also supports uncompressed files.

>[!IMPORTANT]
>
>We don't support encryption on inbound files compressed using gzip (`.gz`).
>
>To encrypt and compress inbound files, use [PGP encryption](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] encryption includes file compression.

## Amazon S3 Compression

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. Compressed files must be 1 GB or smaller. If the files are larger, please discuss the file and transfer process with Customer Care. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>Your [!DNL FTP] client must use binary mode to transfer compressed or encrypted files. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## Best Practices

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension).
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* Optimal split sizes, for fastest/earliest processing of your files, is approximately 1 GB uncompressed or 200-300 MB compressed.
* [!DNL Amazon S3] imposes its own, 5 GB file size limit on uploaded files.
