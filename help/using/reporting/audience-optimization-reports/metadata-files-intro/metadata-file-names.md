---
description: Name your Audience Optimization metadata file according to these specifications.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: Naming Conventions for Metadata Files
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
---

# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

Name your Audience Optimization metadata file according to these specifications.

## Syntax and ID Categories {#syntax}

The following syntax defines the structure of a well-formed metadata file name. Note, *italics* indicates a variable placeholder. The other elements are constants and do not change.

**Syntax:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Do not* use file extensions in your metadata files (.txt or other).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md#concept_5E422498650E40FD9744ABF290750107). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* The child ID can have a value between 1 and 10, depending on the dimension. See below:

## Child ID dimensions {#child-dimension}

In the metadata file name, the child ID is an identifier that classifies the type of data in a file and places it into a hierarchy. You can tag the child ID in file name with the following category IDs:

1. Campaign
1. Creative
1. Placement
1. Exchange
1. Site
1. Advertiser (if using integration codes in a [data source](../../../features/data-sources/manage-datasources.md#details))
1. Insertion Order (IO)
1. Vertical (i.e., a specific industry or business category like "computers," "automobiles," "real estate," etc.)
1. Tactic
1. Business unit or brand

## Example {#example}

For a Creative metadata file, the file name could be 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
