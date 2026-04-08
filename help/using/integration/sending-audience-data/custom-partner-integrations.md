---
description: This page lists custom integrations between Audience Manager and data partners.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Custom Partner Integrations
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
TQID: https://experienceleague.adobe.com/0QvyTQOmjkES1ZO47uu7JTh07-5--uHIgCbJ9iAYfrE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
    internal-label: Audience Marketplace
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Custom Partner Integrations {#custom-partner-integrations}

This page lists custom integrations between Audience Manager and data partners.

## Oracle Data Cloud {#oracle-data-cloud}

### Description

Audience Manager ingests cookie and mobile ID data from the Oracle Data Cloud for Audience Marketplace via inbound data files. The custom integration specifications described below refer only to inbound data files that contain mobile IDs (IDFA and Android Device IDs).

### Integration specifics

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

The elements highlighted below are required, in addition to the standard implementation fields for inbound data files. For descriptions of all other standard fields and file name elements, see File Name Syntax and File Content Syntax in the two pages linked above.

### File naming

ODC file names are structured as:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.

### File contents

Fields in the ODC inbound data file must appear in the order shown below:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

The `ID type` can be:

* IDFA
* Android Device ID

>[!IMPORTANT]
>
>Do not send IDFA and Android Device IDs in the same inbound data file.

## Sample ODC inbound file

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). This file qualifies several IDFAs for the trait ID 38838. You can open this file in a standard text editor or code editor.
