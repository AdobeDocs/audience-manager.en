---
description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
keywords: segment size estimator;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Folder Traits  About
uuid: 3b66e378-b17d-4934-a1d2-48783066d4db
index: y
internal: n
snippet: y
translate: y
---

# Folder Traits: About

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../../c_features/c_tb_overview/folder-traits/about-folder-traits.md#section_1CF315E0BC734FD69B0725F2ADBA1B1B" format="dita" scope="local"> Benefits of Using Folder Traits </a> </li> 
 <li> <a href="../../../c_features/c_tb_overview/folder-traits/about-folder-traits.md#section_7BBCE65C238C467599ECCACC4597D296" format="dita" scope="local"> Folder Traits Realization - Recency and Frequency </a> </li> 
 <li> <a href="../../../c_features/c_tb_overview/folder-traits/about-folder-traits.md#section_FF4A75E342A043F3914873CC0657E0EE" format="dita" scope="local"> Folder Trait Reporting </a> </li> 
 <li> <a href="../../../c_features/c_tb_overview/folder-traits/about-folder-traits.md#section_FB11C9F6F6F542328A6F1F22C40C2220" format="dita" scope="local"> Role-Based Access Controls (RBAC) Permissions </a> </li> 
 <li> <a href="../../../c_features/c_tb_overview/folder-traits/about-folder-traits.md#section_9680EBC0F862495B9E3272D001395794" format="dita" scope="local"> Limits and Other Considerations </a> </li> 
</ul>



## Benefits of Using Folder Traits {#section_1CF315E0BC734FD69B0725F2ADBA1B1B}

A folder trait contains all the traits in a parent folder and its associated child folders. This lets you automatically segment and target your users at different folder levels. For example, let's say you have a folder structure like this: 


* Electronics (parent) 
    * Laptops (child)     
        * Brands (grandchild)




Folder traits qualify all the users in these folders in an automatically created Electronics Folder Trait (based on the name of the parent folder). And, this process repeats itself as you move down the file structure. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops Folder Trait. 

Folder traits are selectable in segment expressions. Selecting a folder trait is equivalent to selecting all the traits within that folder and its subfolders with an "OR" grouping. 

![](assets/folder_traits_compare_border.jpg) 

## Folder Traits Realization - Recency and Frequency {#section_7BBCE65C238C467599ECCACC4597D296}

The frequency count of a folder trait is the sum of realizations of the traits in its folder and its child folders. The illustration below shows traits A, B and C, which live in the Automobile folder. Consider that each of the traits have the following realizations: 


* Trait A: 5
* Trait B: 1
* Trait C: 1


In this case, the Automobile Folder Trait has 7 realizations. 

![](assets/folder_traits_rollup_border.png) 

## Folder Trait Reporting {#section_FF4A75E342A043F3914873CC0657E0EE}

Folder traits capture all the users from the traits in the folder structure below them. If you move a trait from a folder to another folder, the change propagates to our [ data collection servers](../../../c_reference/c_compintro/c_compcollect.md#concept_66CFFEBF5E8B41ED94082D562A93506E) just like a trait rule change. The reporting updates in the next reporting run to reflect this change across the reporting date ranges (1, 7, 14, 30, 60, 90, lifetime). The old reporting numbers from the previous days will not change. 

## Role-Based Access Controls (RBAC) Permissions {#section_FB11C9F6F6F542328A6F1F22C40C2220}

For companies using Role-Based Access Controls (RBAC), your users with the appropriate RBAC permissions are able to change the data source associated to the folder trait. A user must belong to a group with either of the following: 


* READ and WRITE group permissions to a trait data source.
* VIEW_ALL_TRAITS and EDIT_ALL_TRAITS wild card permissions for trait data sources.


Learn how to assign RBAC permissions in our [ administration documentation](../../../c_features/c_administration/t_create_groups.md#task_3327F7C4A9834F1BA5007EDA279D40F2). 

## Limits and Other Considerations {#section_9680EBC0F862495B9E3272D001395794}



|  Item  | Description  |
|---|---|
|  Trait type  | Onboarded traits and algorithmic traits contribute at most 1 realization to a folder trait's frequency.  |
|  Moving traits between folders  | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second folder trait. This means that if you delete or move a trait from the folder, the users in the trait's population will be unsegmented from the segments using the folder trait as a segment expression.  |
|  System variables  |Folder traits cannot be realized in event calls using the ` d_sid` parameter.  |
|  Reporting  |Folder traits are autocalculated traits and do not appear in **[!UICONTROL  Overlap Reports]**.  |

