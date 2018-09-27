---
description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting. Currently, Profile Merge Rules work with real-time destinations only.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting. Currently, Profile Merge Rules work with real-time destinations only.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: General Use Cases for Profile Merge Rules
uuid: f4b80b6a-89df-429e-9b6f-629ca6f1d217
index: y
internal: n
snippet: y
translate: y
---

# General Use Cases for Profile Merge Rules

Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting. Currently, Profile Merge Rules work with real-time destinations only.



![](assets/merge-rules-options.png) 



>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../c_features/profile-merge-rules/merge-rule-definitions.md#concept_44FFF67CD9654DB2B43ECA13C2FD1CE0). 



Contents: 



<ul class="simplelist"> 
 <li><a href="../../c_features/profile-merge-rules/merge-rule-targeting-options.md#section_DD5CB340BF0C4C6F93C640ACA100EDB6" format="dita" scope="local"> Focus targeting</a> </li> 
 <li> <a href="../../c_features/profile-merge-rules/merge-rule-targeting-options.md#section_ADA0946192274869B94BD88BEE8ECFA7" format="dita" scope="local"> Expand targeting</a> </li> 
 <li><a href="../../c_features/profile-merge-rules/merge-rule-targeting-options.md#section_F6D35A63A04346EE85DE533A43E5EE0D" format="dita" scope="local"> Device Graph Options</a> </li> 
</ul>



## Focus targeting {#section_DD5CB340BF0C4C6F93C640ACA100EDB6}



User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]: 

* Write traits to the authenticated profile specific to a particular user.
* Identify and differentiate between multiple device users for segmentation.




**Reach authenticated users** 


The authenticated profile options create rules let you reach users who are logged on to a website or app. For example, a financial services company would use this option to target authenticated users with credit card upgrade offers or specialized service offers based on income or account activity. Another example would be an airline targeting authenticated frequent fliers with deals based on accrued mileage. 


To create a rule that reaches authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. These options tell your rule to use an authenticated profile only. This rule will ignore data in the anonymous device profile. 


**Reach users based on previous authentication state** 


These options reach specific users when they're browsing but not logged on. You can do this with options that rely on inferred user-level targeting. Inferred targeting helps you reach people who are not explicitly authenticated to your site but may be browsing online. It works by reading (but not writing) data from the last authenticated profile. And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. For example, say you're a marketer that wants to test different offers with existing customers who are not logged on to your site or app. As a marketer, you can test these ads with current, un-authenticated customers to see which offers get the most response. 


Rules that reach users based on previous authentication include: 

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**
* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Merge Device Graph]**



## Expand targeting {#section_ADA0946192274869B94BD88BEE8ECFA7}



Along with rules that help reach specific customers, marketers also need rules that increase the size of data sets available for targeting. [!UICONTROL Profile Merge] lets you do this with the device profile options. The device options expand the data set eligible for segmentation because they draw on traits realized while a user was in an unauthenticated state on the device. For example, this could be useful when you're trying to reach everyone in a household (household-level targeting) or all the users who share a device. A use case for these options could include advertising a family vacation offer. In this case, you'll want to reach everyone using a device or in a household. 


To create a rule that expands the targeting data set, select **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**. 

<!-- <p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <span class="uicontrol"> Current Authenticated Profiles</span> + <span class="uicontrol"> Profile Merge Device Graph</span> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <span class="uicontrol"> Last Authenticated Profiles</span> + <span class="uicontrol"> Profile Merge Device Graph</span> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <span class="uicontrol"> No Authenticated Profile</span> + 
  <span class="uicontrol"> Current Device Profile</span> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p> -->

## Device Graph Options {#section_F6D35A63A04346EE85DE533A43E5EE0D}



Choosing a device graph option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. These general guidelines can help you understand when to use one type of graph vs another. Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. Refer to the table below for general guidance on when to choose a device graph option. For specific use cases, see [Profile Link Device Graph Use Cases](../../c_features/profile-merge-rules/profile-link-use-case.md#concept_5D9D32E18BB94F318A8BA0229335F1B9) and [External Device Graph Use Cases](../../c_features/profile-merge-rules/external-graph-use-cases.md#concept_7C0BDBFB3392415286B624F45E8883E5). 




<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Device Graph Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profile Merge</span> rules built with the <span class="wintitle"> Profile Link</span> option are ideal for: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digital properties that have a high-level of customer authentication. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Focused, low-reach campaigns. The <span class="wintitle"> Profile Link</span> device graph is built on deterministic data only. This pool of device profiles will always be smaller relative to the pool of unauthenticated users and devices. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Use cases where customers need to be in an authenticated state to qualify for segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>External Device Graph Options </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profile Merge</span> rules built with the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a> or any external device graph integrated with <span class="keyword"> Audience Manager</span> are ideal for: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digital properties that have a low-level of customer authentication. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Broad, high-reach brand campaigns. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Use cases where customers do not need to be in an authenticated state to qualify for segmentation. </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Profile Link Device Graph Use Cases](profile-link-use-case.md#concept_5D9D32E18BB94F318A8BA0229335F1B9)
>* [External Device Graph Use Cases](external-graph-use-cases.md#concept_7C0BDBFB3392415286B624F45E8883E5)
>* [Profile Merge Rules FAQ](faq-profile-merge.md#concept_C8E29A974E194B62B0BAC1CCDD0DF4FF)
