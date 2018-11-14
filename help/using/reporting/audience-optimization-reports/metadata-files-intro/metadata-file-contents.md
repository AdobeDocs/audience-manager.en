---
description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Content Format for Metadata Files
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
index: y
internal: n
snippet: y
---

# Content Format for Metadata Files{#content-format-for-metadata-files}

Format the contents of your Audience Optimization metadata file according to these specifications.

## Syntax {#section_FA6B6FE02D93456EB3A64488E0FA8DC7}

The following syntax defines the structure of well-formed contents in a metadata file. Note, *italics* indicates a variable placeholder.

**Syntax:** ` *`content ID`* | *`name`* | *`parent ID`*`

In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#concept_729806531D4547A6B5870BEA199FB4A9). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:

* The parent ID is the numeric ID of the object that the file contents belong to. For example, if your file contains creatives in a campaign, this value is the campaign ID. 
* If your file content *does not* have a parent ID, then use the `NULL` object (i.e., the non-printing programming object) or `-1`. You would use `NULL` or `-1` when the parent ID in the file name is set to ID 0.

**Separate File Entries With ASCII 001 or Tab**

The non-printing ASCII 001 character is the preferred delimiter for separating contents in your file. If you cannot use ASCII 001, then separate file contents with a tab delimiter. As these are non-printing characters, the syntax example above shows a pipe "|" for display purposes only.

## Examples {#section_08FE1874E7F64774999335D49011E0B5}

Let's take a look at how you would structure content in a metadata file. Part of this structure depends on the type of information categorized by the parent ID the file title.

**With a Parent Object**

Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.

```
//file title
20150827_1_2

//creative IDs, names, and campaign IDs
111 Creative A 456
222 Creative B 456
333 Creative C 987

```

**Without a Parent Object**

Sometimes, the content in a metadata file does not have a parent object. In these cases, the:

* File name parent ID is 0. 
* File content parent ID is the non-printing `NULL` object (preferred) or -1.

```
//file title
20150827_0_2

//file contents: creative IDs, names, and campaign IDs
888 Creative X NULL
777 Creative Y NULL
666 Creative Z NULL
```

