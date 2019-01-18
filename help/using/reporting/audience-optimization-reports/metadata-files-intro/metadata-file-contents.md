---
description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Content Format for Metadata Files
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
---

# Content Format for Metadata Files{#content-format-for-metadata-files}

Format the contents of your Audience Optimization metadata file according to these specifications.

## Syntax {#section_FA6B6FE02D93456EB3A64488E0FA8DC7}

The following syntax defines the structure of well-formed contents in a metadata file. Note, *italics* indicates a variable placeholder.

**Syntax:**  *content ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#concept_729806531D4547A6B5870BEA199FB4A9). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>Note that one metadata file per dimension is needed, so multiple metadata files are expected in the bucket. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).
  

**Separate File Entries With ^a (control-A or ASCII 001)**

Use ^a (control-A or ASCII 001) to separate content in your metadata files. As these are non-printing characters, the syntax example above shows a pipe "|" for display purposes only.

If needed, you may download this example file **![(20181105_0_1)](assets/20181105_0_1)** in your editor of choice and adjust according to your actual metadata contents, as it already contains the required delimiter.

>[!IMPORTANT]
>
>Do not add header rows to metadata files.

## Examples {#section_08FE1874E7F64774999335D49011E0B5}

Let's take a look at how you would structure content in a metadata file. Part of this structure depends on the dimension. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension). 

**Campaign**

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

//Campaign ID, Name, and Parent ID
111 Campaign A -1
222 Campaign B -1
333 Campaign C -1

```

**Creative**

```
//file title
20150827_0_2

//file contents: creative IDs, names, and campaign IDs
888 Creative X NULL
777 Creative Y NULL
666 Creative Z NULL
```

**Site**

```

//File Title
20180921_0_5

//Site ID, Name, and Parent ID
111 Site A -1
222 Site B -1
333 Site C -1

```

