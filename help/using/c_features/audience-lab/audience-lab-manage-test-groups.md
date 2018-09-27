---
description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Manage Test Groups
uuid: 25d2f15f-22ea-432d-bda1-1461914adb54
index: y
internal: n
snippet: y
translate: y
---

# Manage Test Groups

This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab

## Manage Test Groups {#topic_A85450A5B5F34C2694DC2E7154C0C60F}

This procedure walks you through the steps needed to create, edit, or delete a test group in 
<wintitle>
  Audience Lab 
</wintitle>

## Create Segment Test Group {#task_B62EF6D2992941FAAEA84BE2EA11A55E}



**Prerequisites** 

<!-- create-test-group.xml -->



* You need to have at least one **conversion trait** set up. You can set up conversion traits in the Trait Builder, by selecting **conversion** as the [Event Type](../../c_features/traits/create-onboarded-rule-based-traits.md#concept_D80233EF56764376B0F4C4FF882BAD2E). 
  >[!IMPORTANT]
  >
  >Folder traits are**not supported** by [!UICONTROL Audience Lab]. Setting the [Event Type](../../c_features/traits/create-onboarded-rule-based-traits.md#concept_D80233EF56764376B0F4C4FF882BAD2E) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait. 

* For companies using [Role-Based Access Control](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../c_features/c_administration/administration-overview.md#concept_29BA0C02C1864F3BBB1D322F8A400A2D) to **[!UICONTROL User Groups]** to provide access. This permission allows the user to create and view the results of a test. A user will only be able to use segments from a data source they have **"read" **and** "map to destination"** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. A user will only be able to see destinations they have access to as well. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has: 
    * access to read relevant conversion traits;    
    * access to read and map relevant segments for tests;    
    * access to relevant destinations.    
    
    






**To create a new Segment Test Group** 

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

    * 
    
      Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**. 
    
    * 
    
      Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]** 
    
    * 
    
      You can save the test group as a draft and resume working on it later. 
    
    * 
    
      An alert will show up in case the base segment you selected is already used in other test groups. Using the base segment twice may distort the conversion results for both tests. 
    
    
    
1. **[!UICONTROL Allocate Test Segments]**

    * 
    
      You can create **up to 15 test segments** and divide the percentage of devices as you wish. 
    
    * 
    
      You can edit the name of the test segments by clicking on them. 
    
    * 
    
      The percentages automatically divide evenly to 100% when new test segments are allocated. You can then manually edit the percentages. Click the checkbox after editing the percentages and make sure they add up to 100%, otherwise you will not be able to proceed to the next step. 
    
    
    
1. **[!UICONTROL Set a Control Segment]**

    * 
    
      Select a control segment if you want to set aside a certain part of the segment to be used as a control group. Control groups allow you to see the impact of the test segments you created compared to a benchmark. 
    
    * 
    
      You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control. 
    
    * 
    
      Click **[!UICONTROL Next]** when you're done. 
    
    
    
1. **[!UICONTROL Select Conversion Traits]**

    * 
    
      Add conversion traits by typing in the conversion trait window. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait. 
    
    * 
    
      You can add up to 5 conversion traits if you wish. 
    
    * 
    
      An alert will show up in case you select a conversion trait already used for other test groups. 
    
    
    
1. **[!UICONTROL Choose Destinations & Dates]**

    * 
    
      Type in the desired destinations in the search field or use the drop-down arrow. [!UICONTROL Audience Lab] test segments can be sent to URL, cookie, or server-to-server destinations. 
    
    * 
    
      Drag & drop segments to destinations. 
    
    * 
    
      After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind. 
    
    * 
    
      You can send the same test segment to multiple destinations and you can add multiple test segments to a single destination. 
    
    * 
    
      Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../c_features/data-export-controls.md#concept_155AAFBA7D804467B6F8279D26C9D05C). 
    
    * 
    
      Users will only see the destinations they have access to based on the [RBAC User Group](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296) they belong to. 
    
    * 
    
      Finally, you are required to select a start date for your test group. This date marks the start of the period in which your test group will be published to destinations. Select **No End Date** for an indefinite comparison of the test segments. 
    
    
    


   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] with an authenticated profile are only supported in Real-time destinations. If a test segment with a profile merge rule of that configuration is sent to a file-based server-to-server destination, the audiences might not populate. 
   **[!UICONTROL Next]**1. **[!UICONTROL Summary & Finalize]**

    * 
    
      Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**. 
    
    * 
    
      Remember that once you finalize a test group, it can be duplicated or deleted, but not edited. 
    
    
    




   >[!NOTE]
   >
   >
   >* You can save the test groups at any point in the creation process and return to the wizard at a later time. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.   >
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.   >
   >
   >


## Edit Segment Test Group {#task_F24DC69FC0AA45D9AB604DA7638799E9}

In 
<wintitle>
  Audience Lab 
</wintitle>, you are only able to edit draft test groups. In the 
<wintitle>
  Create Segment Test Group 
</wintitle> wizard, you can save your test group as a draft and resume working on it later.


1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../c_features/audience-lab/audience-lab-manage-test-groups.md#task_B62EF6D2992941FAAEA84BE2EA11A55E) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#task_4EDCDE99FF8C4107BA916C3D0DC281BE}


1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Find the test group you want to delete. You can either:

    * press the **[!UICONTROL Delete]** control in the test group card, or    
    * press the test group title in the test group card to go to the [Test Group Information](../../c_features/audience-lab/audience-lab-information-view.md#concept_C8A8844639CE41E9AE9D6886D829B8E0) view and press the **[!UICONTROL Delete]** control in the title bar.    
    
    
1. For [completed test segments](../../c_features/audience-lab/audience-lab.md#section_4A6E6FC7095B4F13A8CEC8E2EBC01EBF), an alert will prompt you to download the CSV file to save the reporting if you wish.
