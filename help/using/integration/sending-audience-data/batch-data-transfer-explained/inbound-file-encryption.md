---
description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: File PGP Encryption for Inbound Data Types
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
---
# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

You can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] encryption includes file compression. When sending [!DNL PGP] encrypted inbound files make sure you don't [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) them using gzip (`.gz`).
>
>[!DNL PGP] encrypted inbound files that are also [compressed](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) are invalid in Audience Manager.

Follow the steps outlined below to encrypt inbound data files.

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
2. Import the public key to your trusted store.

   For example, if you use [!DNL GPG], the command could be similar to the following:
   
   `gpg --import adobe_pgp.pub`
   
3. Validate that the key has been imported correctly by running the following command:

    `gpg --list-keys`

    You should see a message similar to the following:

    ```
    pub   4096R/8496CE32 2013-11-01
    uid                  Adobe AudienceManager
    sub   4096R/E3F2A363 2013-11-01
    ```

4. Encrypt the inbound data using the following command:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager supports any key size.
