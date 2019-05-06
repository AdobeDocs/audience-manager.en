---
description: This page lists custom integrations between Audience Manager and data partners.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Custom Partner Integrations
---

# Custom Partner Integrations {#custom-partner-integrations}

This page lists custom integrations between Audience Manager and data partners.

## Oracle Data Cloud {#oracle-data-cloud}

**Description**

Audience Manager ingests cookie and mobile ID data from the Oracle Data Cloud for Audience Marketplace via inbound data files. The custom integration specifications described below refer only to inbound data files that contain mobile IDs (IDFA and Android Device IDs).


**Integration specifics**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

The elements highlighted below are required, in addition to the standard implementation fields for inbound data files. For descriptions of all other standard fields and file name elements, see File Name Syntax and File Content Syntax in the two pages linked above.


**File naming**

ODC file names are structured as:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.


**File contents**

Fields in the ODC inbound data file must appear in the order shown below:

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* Android Device ID

>[!IMPORTANT]
>
>Do not send IDFA and Android Device IDs in the same inbound data file.


**Sample ODC inbound file**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). This file qualifies several IDFAs for the trait ID 38838. You can open this file in a standard text editor or code editor.