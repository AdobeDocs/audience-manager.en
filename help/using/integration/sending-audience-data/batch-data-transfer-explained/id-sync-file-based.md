---
description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Name and Content Requirements for ID Synchronization Files
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
---

# Name and Content Requirements for ID Synchronization Files {#name-and-content-requirements-for-id-synchronization-files}

Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.

>[!NOTE]
>
>The text styles (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../../reference/code-style-elements.md) for more information.

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID file names contain the following required and optional elements:

`adobe_id_`*`[c2c_id_]`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file. Use this prefix when matching device IDs to other device IDs or customer IDs (DPUUIDs).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file for People-Based Destinations. Use this prefix when matching customer IDs (DPUUIDs) to hashed email addresses for People-Based Destinations.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> The master data provider ID is the parent ID of the DPIDs in the file name. Also, the first user ID in the data file corresponds to the master ID. The subsequent DPIDs are other identifiers that belong to the master. Synchronization maps DPIDs in the file name to UUIDs in the file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Data provider IDs. These IDs represent entities or data sources associated with the master DPID. Synchronization maps DPIDs in the file name to UUIDs in the file. </p> <p>The number of DPIDs in the file name must match the number of UUIDs in the data file. For example, say your file name contains a master DPID and 3 DPIDs. Your data file must include 4 corresponding columns of UUIDs, formatted as described in the file content section below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>A 10-digit, UNIX timestamp in seconds. The timestamp helps make each file name unique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indicates a normal, full synchronization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>An integer. Used when you split large files into multiple smaller files. This helps improve processing times. The number indicates which part of the original file you're sending in. See the file name examples below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Specifies that your file is compressed with optional gzip compression. </p> </td> 
  </tr> 
 </tbody> 
</table>

### File Name Examples

The following examples show properly formatted files names. Your file names could look similar.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> For ID synchronization file naming (c2c prefix) for People-Based Destinations, see [Workflow A - Personalization Based on All Online Activity Combined with Offline Data](../../../features/destinations/people-based-destinations-workflow-combined.md) or [Workflow B - Personalization Based on Offline-Only Data](../../../features/destinations/people-based-destinations-workflow-offline.md).

## File Content Syntax and Examples {#file-content-syntax}

The contents of an ID file include the following elements:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs ([!DNL UUID]). In each row, separate the IDs with a tab. The following example shows a properly formatted ID file. Your contents could look similar.

```
abc123 def456 ghi789 xyz987
```

## Synchronization Matches DPUUIDs to UUIDs {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the [DPUUIDs](../../../reference/ids-in-aam.md) from your own Data Sources with [!DNL Audience Manager] UUIDs. Synchronization maps the [!DNL DPUUID]s from the master [!DNL DPID] and its related [!DNL DPID]s to the [!DNL Audience Manager] [!DNL UUID]s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. For example, take the two sample files shown here:

* **File 1:** `adobe_id_0_12345_1476312152.sync`

* **File 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Given the sample name and contents, the IDs map together like this:

**File 1** ( [Download sample file](assets/adobe_id_0_12345_1476312152.sync))

|  DPID 0 = Adobe Audience Manager UUIDs  | DPID 12345  |
|---|---|
|  68079982765673198504052656074456196039  | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38  |
|  67412682083411995725538770443620307584  | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70  |
|  89159024796760343733111707646026765593  | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM  |
|  66552757407517449462805881945288602094  | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M  |
|  66184778222667870903738139438735041506  | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw  |

Step 1: the ID sync process will sync the [!DNL DPUUID]s from [!DNL DPID] 12345 with the [!DNL Audience Manager] [!DNL UUID]s in the left column. Note that the [!DNL DPID] "0" in the file name represents [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**File 2** ( [Download sample file](assets/adobe_id_12345_67890_1477846458.sync))

|  [!DNL DPID] 12345  | [!DNL DPID] 67890  |
|---|---|
|  XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38  | 4598060374  |
|  XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70  | 4581274262  |
|  XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM  | 4392434426  |
|  XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M  | 2351382994  |
|  XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw  | 4601584763  |

Step 2: the [!DNL DPUUID]s from [!DNL DPID] 12345 have been synced in step 1 with the Audience Manager [!DNL UUID]s. What this ID sync will do is sync the [!DNL DPUUID]s from [!DNL DPID] 67890 with the Audience Manager [!DNL UUID]s from step 1.

<br/>

## Other Format Requirements {#other-format-reqs}

User IDs cannot:

* Have tabs in the ID itself. Tabs are used only to separate individual IDs in the data file.
* Contain personally identifiable information ([!UICONTROL PII]).
* Use [!DNL URL] encoding. Pass in unencoded IDs only.

Any rows that end with tabs or spaces will not be processed or realized. As a rule, make sure you keep the end of the rows clear.