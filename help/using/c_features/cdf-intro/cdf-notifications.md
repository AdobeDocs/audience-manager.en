---
description: Audience Manager writes a .info file to your S3 directory to let you know when your Customer Data File (CDF) is ready for download. The .info file also includes JSON-formatted metadata about the contents of your CDF files. Review this section for information about the syntax and fields used by this notification file.
seo-description: Audience Manager writes a .info file to your S3 directory to let you know when your Customer Data File (CDF) is ready for download. The .info file also includes JSON-formatted metadata about the contents of your CDF files. Review this section for information about the syntax and fields used by this notification file.
seo-title: Customer Data Feed File Processing Notifications
solution: Audience Manager
title: Customer Data Feed File Processing Notifications
uuid: 438914bc-00fa-48f2-8b6c-d850901e16af
index: y
internal: n
snippet: y
translate: y
---

# Customer Data Feed File Processing Notifications


## Sample Info File {#section_BC331FC87C5A4BC9AE799B53F4FAA3E7}

Each ` .info` file contains a ` Files` and ` Totals` section. The ` Files` section contains an array that holds specific metrics for each hourly file. The ` Totals` section contains metrics aggregated across all your CDF files for a particular day. The contents of your ` .info` file could look similar to the following example. 


```
js{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```


## Info File Fields Defined {#section_24CE58EEA37347B58C4C02E1B7BF5278}

The following tables list and defines the elements in a CDF ` .info` file. 

**Files Object** 



<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Files</span> </p> </td> 
   <td colname="col2"> <p>Starts the array that contains metadata about your CDF files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> FileByteSize</span> </p> </td> 
   <td colname="col2"> <p>File size in bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> FileChecksumMD5</span> </p> </td> 
   <td colname="col2"> <p>The Amazon S3 ETag. The digit following the hyphen shows the number of parts used to build the file during the multi-part upload. The ETag is not identical to the MD5 checksum of the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> FileName</span> </p> </td> 
   <td colname="col2"> <p>The file name. See <a href="../../c_features/cdf-intro/cdf-file-name.md#reference_DAC53BEEA60B426588D1B66B3B92E8C1" format="dita" scope="local"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> FileSequenceNumber</span> </p> </td> 
   <td colname="col2"> <p>An index number for each file. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Totals Object** 



<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Totals</span> </p> </td> 
   <td colname="col2"> <p>Starts the object that contains aggregated data about all your CDF files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Day</span> </p> </td> 
   <td colname="col2"> <p>The day for which the data is available. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Hour</span> </p> </td> 
   <td colname="col2"> <p>The hour for which data is available. Uses 24-hour format set in UTC time zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TotalByteSize</span> </p> </td> 
   <td colname="col2"> <p>Total size of all your CDF files for that date in bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> TotalNumberFiles</span> </p> </td> 
   <td colname="col2"> <p>Total number of files uploaded to your S3 directory. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ Customer Data Feed File Name Times and File Content Times... ](cdf-time-differences.md#concept_C907608AC1ED44BA8EF870F45E5A9CB9)
>* [ Customer Data Feed FAQ ](cdf-faq.md#concept_E832A7307FA0475C918F95116C21CBC6)
