---
description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: Transfer-Control Files for Log File Transfers
uuid: ef58213e-7b37-4c5a-8556-0de695706793
---

# Transfer-Control Files for Log File Transfers{#transfer-control-files-for-log-file-transfers}

Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] sends a transfer-control file to a partner with every file transfer. Due to the multi-thread nature of the FTP publisher, the transfer-control file might be sent before the actual files are finished transferring.

The metadata in the [!DNL .info] file lets partners:

* Determine when a full transfer cycle is complete (the total number of files in the sequence have been delivered) 
* Determine whether any given file in the sequence is complete/correct (by examining the size of the file in bytes and the total number of lines) 
* Validate the number of rows in raw files verses the number of rows after the files have been loaded in the database on the receiving end (size of file in lines)

## File Naming Conventions {#section_6C0CE366AABD4870B5E34FA6FC8EF9AE}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

## File Format {#section_5D988BA77A014EFD805A6A010311A98D}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

**Notes:**

The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.

Byte sizes of files and line counts are inclusive of any header and spacer (blank) lines/rows. In order to get the count of actual data lines/rows, subtract headers.

Total lines in batch and total byte size are inclusive of any header and space rows. 
