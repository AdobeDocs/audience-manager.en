---
description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Content Format for Metadata Files
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
---
# Content Format for Metadata Files{#content-format-for-metadata-files}

Format the contents of your Audience Optimization metadata file according to these specifications.

## Syntax {#syntax}

The following syntax defines the structure of well-formed contents in a metadata file. Note, *italics* indicates a variable placeholder.

**Syntax:**  *content ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>Note that one metadata file per dimension is needed, so multiple metadata files are expected in the bucket. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).
  
**Separate File Entries With ^a (control-A or ASCII 001)**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. As these are non-printing characters, the syntax example above shows a pipe "|" for display purposes only.

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). Unzip it and edit in your editor of choice and adjust according to your actual metadata contents, as it already contains the required delimiter.

>[!IMPORTANT]
>
>Do not add header rows to metadata files.

## Examples {#examples}

Let's take a look at how you would structure content in a metadata file. Part of this structure depends on the dimension. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

In this example, the file title is 20180921_0_1 and the three columns in the file are: Campaign ID, Name, and Parent ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1

```

**Creative**

In this example, the file title is 20180827_0_2 and the three columns in the file are: Creative ID, Name, and Parent ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

In this example, the file title is 20180921_0_5 and the three columns in the file are: Site ID, Name, and Parent ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1

```
