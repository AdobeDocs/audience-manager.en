---
description: Name your Audience Optimization metadata file according to these specifications.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: Naming Conventions for Metadata Files
uuid: 66719567-5f67-4d91-ac6a-59d445c6445c
index: y
internal: n
snippet: y
translate: y
---

# Naming Conventions for Metadata Files

Name your Audience Optimization metadata file according to these specifications.


## Syntax and ID Categories {#section_9CBA80B3F506437586F8CE48F4F6ECBC}



The following syntax defines the structure of a well-formed metadata file name. Note, *italics* indicates a variable placeholder. The other elements are constants and do not change. 


**Syntax:** ` *`yyyymmdd`*_ *`parentID`*_ *`childID`*` 


In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md#concept_5E422498650E40FD9744ABF290750107). These 2 variables seem similar, but they represent different things: 

* In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc.
* In the file body, the parent ID is the actual ID of the object that the contents belong to. For example, if your file contains creatives that are part of a campaign, the parent ID is the actual ID of the campaigns these creatives belong to.




**Metadata File ID and Categories** 


In the metadata file name, the parent and child IDs are identifiers that classify the type of data in a file and place it into a hierarchy. You can tag the parent and child elements in file name with the following category IDs: 

* 0: No parent
* 1: Campaign
* 2: Creative
* 3: Placement
* 4: Exchange
* 5: Site
* 6: Advertiser (if using integration codes in a [data source](https://marketing.adobe.com/resources/help/en_US/aam/?f=t_create_edit_datasource.html))
* 7: Insertion Order (IO)
* 8: Vertical (i.e., a specific industry or business category like "computers," "automobiles," "real estate," etc.)
* 9: Tactic
* 10: Business unit or brand



## Example {#section_A613DDC627444B2EBA6D5D6AAB42ACD6}



Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name: 

* Parent ID: `1`
* Child ID: `2`




Your metadata file name would look like this: `20150827_1_2` 


Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. 
