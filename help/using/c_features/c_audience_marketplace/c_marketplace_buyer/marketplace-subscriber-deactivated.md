---
description: In Audience Marketplace, Data Providers can revoke access to your subscribed data feeds. Don't be alarmed if this happens to you. We've got you covered. Review this section for processes and procedures related to data feed deactivations.
seo-description: In Audience Marketplace, Data Providers can revoke access to your subscribed data feeds. Don't be alarmed if this happens to you. We've got you covered. Review this section for processes and procedures related to data feed deactivations.
seo-title: Data Feed Deactivation  Why It Happens and How to Respond
solution: Audience Manager
title: Data Feed Deactivation  Why It Happens and How to Respond
uuid: 5a0281a1-0d3e-4a8b-a44a-a9b90f318d54
index: y
internal: n
snippet: y
translate: y
---

# Data Feed Deactivation: Why It Happens and How to Respond

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../../c_features/c_audience_marketplace/c_marketplace_buyer/marketplace-subscriber-deactivated.md#section_D35C33B3D1AE467FBC22AFB7B1982EB9" format="dita" scope="local"> Common Reasons for Data Feed Deactivation </a> </li> 
 <li> <a href="../../../c_features/c_audience_marketplace/c_marketplace_buyer/marketplace-subscriber-deactivated.md#section_B195EA48C18B4F978070F7F198995CB5" format="dita" scope="local"> Deactivation Email </a> </li> 
 <li> <a href="../../../c_features/c_audience_marketplace/c_marketplace_buyer/marketplace-subscriber-deactivated.md#section_36CECC9A202A43AD94202EE03B8FA5FC" format="dita" scope="local"> Deactivated Trait List </a> </li> 
 <li> <a href="../../../c_features/c_audience_marketplace/c_marketplace_buyer/marketplace-subscriber-deactivated.md#section_69CBB45889874E1182E4A8A92D1BE709" format="dita" scope="local"> Remove Deactivated Traits </a> </li> 
</ul>



## Common Reasons for Data Feed Deactivation {#section_D35C33B3D1AE467FBC22AFB7B1982EB9}

It may be puzzling or even upsetting if a feed you subscribe to is shut off. However, Data Providers can deactivate a data feed for a variety of reasons. Some common reasons include: 


* **Billing:** Data Providers will deactivate a feed if you're consistently late with fee payments or if you fail to pay your fees.
* **Feed Updates:** Data Providers need to deactivate feeds when they update their feed taxonomy or cost structures.
* **Inactive Buyers:** Data Providers reserve the right to deactivate feeds if subscribers show no spending over an extended period of time.
* **Inactive Sellers:** Data Providers who leave [!UICONTROL  Audience Marketplace] will deactivate and delete all their data feeds.



>[!TIP]
>
>Contact your Data Provider directly if you believe a data feed was deactivated by mistake. Your [!DNL  Adobe] consultant can help you with contact information or additional support. 



## Deactivation Email {#section_B195EA48C18B4F978070F7F198995CB5}

When a Data Provider deactivates one of your data feeds, [!DNL  Audience Manager] sends an email to the users in your company who have Administrator permissions. Sometimes email filters classify this message as spam. As a result, you may miss this important notification. To help you identify the deactivation message, this email contains the following elements: 

* **From:** The deactivation email comes from ` aam-noreply@adobe.com`. Pro-tip: Don't reply to this email.
* **Subject line:** Subscription to *name of data feed here* is Cancelled.
* **Attachments:**The email includes an attachment titled, " ` list-of-affected-entities-by-feed-revocation.csv`." That's a convoluted way of saying the attachment lists all the traits included in the cancelled feed. As a Data Buyer, you should review this attachment. It will help you find and remove deactivated traits from your segments and [ algorithmic models](../../../c_features/c_models/c_models.md#concept_49FB2DBD4AD041A4ABAAEE9D83BB996E).

## Deactivated Trait List {#section_36CECC9A202A43AD94202EE03B8FA5FC}

The list that accompanies a deactivation email contains the fields as shown below. 



<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data Feed ID </p> </td> 
   <td colname="col2"> <p>ID of the deactivated data feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Feed Name </p> </td> 
   <td colname="col2"> <p>Name of the deactivated data feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trait SID </p> </td> 
   <td colname="col2"> <p>Deactivated trait IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trait Name </p> </td> 
   <td colname="col2"> <p>Deactivated trait names. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segment SID </p> </td> 
   <td colname="col2"> <p>ID of the segment that contains deactivated traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segment Name </p> </td> 
   <td colname="col2"> <p>Name of the segment that contains deactivated traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algo Model ID </p> </td> 
   <td colname="col2"> <p>The ID of the algorithmic model that contain deactivated traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algo Model Name </p> </td> 
   <td colname="col2"> <p>The names of algorithmic models that contain deactivated traits. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Remove Deactivated Traits {#section_69CBB45889874E1182E4A8A92D1BE709}

As a Data Buyer, you're responsible for removing the traits in a cancelled feed from all your active/in-use or inactive segments. Removal options include: 


* Bulk removal with the [ REST APIs](../../../c_api/c_rest_api_main/c_rest_api_main.md#concept_B512E6C3410A4304A672588A60A792B1) or the [ Bulk Management Tools](../../../c_reference/c_bulk/c_bulk.md#concept_8D6CB301643C482F994938F6484B390C).
* Manually search for affected segments and remove deactivated traits using [!UICONTROL  Segment Builder]. See [ Remove Traits from a Segment](../../../c_features/c_segments/c_segment_builder/remove-traits.md#task_D165E279D55A43C7952D936B207FD78A).



>[!NOTE]
>
>Removing traits from active algorithmic models or destinations affects scale and targeting accuracy. Try to replace revoked traits with new, active traits if possible.



[ Unsubscribe from the deactivated data feed](../../../c_features/c_audience_marketplace/c_marketplace_buyer/t_unsubscribe_feed.md#task_10D0EA04E9C34F78A69A71AFA25BD40E) after you remove all the revoked traits from your account. If this is a temporary deactivation, you can re-subscribe after the Data Provider finishes making their required changes and reactivates the feed. As with most things, good communication with your partners (the Data Provider and Adobe) can help you work through this process. 
