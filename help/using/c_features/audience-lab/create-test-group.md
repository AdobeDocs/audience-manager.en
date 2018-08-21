---
description: This procedure walks you through the process of creating a new test group in Audience Lab.
keywords: model;models;lookalike;look-alike;modeling;look-alike modeling
seo-description: This procedure walks you through the process of creating a new test group in Audience Lab.
seo-title: Create Segment Test Groups
solution: Audience Manager
title: Create Segment Test Groups
topic: DIL API
uuid: 9f958340-ad50-4b80-a35a-ae02e4ed1612
index: y
internal: n
snippet: y
translate: y
---

# Create Segment Test Groups

**Prerequisites** 


* You need to have at least one **conversion trait** set up. You can set up conversion traits in the Trait Builder, by selecting **conversion** as the [ Event Type ](../../c_features/c_tb_overview/c_tb_main/c_trait_create/c_tb_basics.md#concept_D80233EF56764376B0F4C4FF882BAD2E). 
  >[!IMPORTANT]
  >
  >Folder traits are**not supported** by Audience Lab. Setting the [ Event Type ](../../c_features/c_tb_overview/c_tb_main/c_trait_create/c_tb_basics.md#concept_D80233EF56764376B0F4C4FF882BAD2E) of a folder trait to **conversion** will not generate any data in Audience Lab for that specific folder trait. 

* For companies using [ Role-Based Access Control ](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296): Assign the [!UICONTROL  Audience Lab] [ wildcard permission ](../../c_features/c_administration/c_wildcard_permissions.md#concept_29BA0C02C1864F3BBB1D322F8A400A2D) to **[!UICONTROL  User Groups]** to provide access. This permission allows the user to create and view the results of a test. A user will only be able to use segments from a data source they have **"read" **and** "map to destination"** privileges for. The user will only be able to use conversion traits from a data source they have the **"read"** permission for. A user will only be able to see destinations they have access to as well. So, before adding the [!DNL  Audience Lab] wildcard permission to a group, make sure the group has: 
    * access to read relevant conversion traits;
    * access to read and map relevant segments for tests;
    * access to relevant destinations.



**To create a new Segment Test Group** 

>1. Select **[!UICONTROL  Create New Test Group]** in the [!UICONTROL  Audience Lab] dashboard to start the wizard.
>1. **[!UICONTROL  Basic Info &amp; Choose Segment]**
>    * Fill in a **[!UICONTROL  Test Group Name]** and a **[!UICONTROL  Description]**. 

>    * Choose the **[!UICONTROL  Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL  Choose Segment.]** 

>    * You can save the test group as a draft and resume working on it later. 

>    * An alert will show up in case the base segment you selected is already used in other test groups. Using the base segment twice may distort the conversion results for both tests. 

>1. **[!UICONTROL  Allocate Test Segments]**
>    * You can create **up to 15 test segments** and divide the percentage of devices as you wish. 

>    * You can edit the name of the test segments by clicking on them. 

>    * The percentages automatically divide evenly to 100% when new test segments are allocated. You can then manually edit the percentages. Click the checkbox after editing the percentages and make sure they add up to 100%, otherwise you will not be able to proceed to the next step. 

>1. **[!UICONTROL  Set a Control Segment]**
>    * Select a control segment if you want to set aside a certain part of the segment to be used as a control group. Control groups allow you to see the impact of the test segments you created compared to a benchmark. 

>    * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL  None]** for no control. 

>    * Click **[!UICONTROL  Next]** when you're done. 

>1. **[!UICONTROL  Select Conversion Traits]**
>    * Add conversion traits by typing in the conversion trait window. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait. 

>    * You can add up to 5 conversion traits if you wish. 

>    * An alert will show up in case you select a conversion trait already used for other test groups. 

>1. **[!UICONTROL  Choose Destinations &amp; Dates]**
>    * Type in the desired destinations in the search field or use the drop-down arrow. [!UICONTROL  Audience Lab] test segments can be sent to URL, cookie, or server-to-server destinations. 

>    * Drag &amp;amp; drop segments to destinations. 

>    * After dropping a segment in a destination, fill in the **[!UICONTROL  Destination Mapping Value]** in the blind. 

>    * You can send the same test segment to multiple destinations and you can add multiple test segments to a single destination. 

>    * Destinations are grayed out if they are not available for a certain test segment based on [ Data Export Controls ](../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C). 

>    * Users will only see the destinations they have access to based on the [ RBAC User Group ](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296) they belong to. 

>    * Finally, you are required to select a start date for your test group. This date marks the start of the period in which your test group will be published to destinations. Select **No End Date** for an indefinite comparison of the test segments. 



>       >[!NOTE]
>       >
>       >Profile Merge Rules with an authenticated profile are only supported in Real-time destinations. If a test segment with a profile merge rule of that configuration is sent to a file-based server-to-server destination, the audiences might not populate.
>       **[!UICONTROL  Next]**1. **[!UICONTROL  Summary &amp; Finalize]**
>    * Review the information you added in the previous steps and select **[!UICONTROL  Finalize Group]**. 

>    * Remember that once you finalize a test group, it can be duplicated or deleted, but not edited. 



>       >[!NOTE]
>       >
>       >
>       >* You can save the test groups at any point in the creation process and return to the wizard at a later time. The test group status will be **[!UICONTROL  Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
>       >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL  Edit]** in the test group card in the main [!UICONTROL  Audience Lab] view.


