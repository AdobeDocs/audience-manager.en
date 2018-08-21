---
description: Plan types are essential components in an Audience Marketplace data feed. As a data provider, they let you create multiple use cases and price options for your feeds. Furthermore, it can be a good strategy to create a few plans for each data feed. This gives buyers different options to choose from when they're looking for data to model or send to a destination.
seo-description: Plan types are essential components in an Audience Marketplace data feed. As a data provider, they let you create multiple use cases and price options for your feeds. Furthermore, it can be a good strategy to create a few plans for each data feed. This gives buyers different options to choose from when they're looking for data to model or send to a destination.
seo-title: Plan Types for Data Feeds
solution: Audience Manager
title: Plan Types for Data Feeds
topic: DIL API
uuid: 51bc42b8-59bd-46ef-b6e1-c1b9cfbb5d5c
index: y
internal: n
snippet: y
translate: y
---

# Plan Types for Data Feeds

[ Create a data feed](../../../c_features/c_audience_marketplace/c_marketplace_provider/t_data_feed.md#task_31BA4FB8FCD940588E6DCE2E7503DF4D) to select [!UICONTROL  Plan Types]. 

![](assets/plan_types.png) 

## Plan Types and Use Case Options {#section_2DDDBB94B8814B80AAF85CB2ABA4DF99}

The [!UICONTROL  Use Case] settings let sellers control how buyers can use your data. 

**Segments and Overlap** 

A **[!UICONTROL  Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a[ trait-to-trait overlap report](../../../c_features/c_analytics/c_dynamic_reports/c_overlap_reports/c_overlap_reports.md#concept_1FBAED029FFD4AA5A5C6E79F633D9A0D). Furthermore, buyers can add your data to segments and make comparisons with the[ segment-to-trait](../../../c_features/c_analytics/c_dynamic_reports/c_segment_trait_overlap/c_segment_trait_overlap.md#concept_36186B1ABEA34A6AAC7F5CF938A122B7) and [ segment-to-segment](../../../c_features/c_analytics/c_dynamic_reports/c_segment_segment_overlap/c_segment_segment_overlap.md#concept_25E40808056B451BA06502A9527A55AA) reports. 

Each Data Feed must include at least 1 Segments and Overlap use case. Buyers cannot subscribe to other plans in a Data Feed if the feed does not contain a Segments and Overlap use case, either by itself or in combination with another use case. 

Overlap comparisons can help buyers: 
* **Extend audience reach:** Low overlap suggest your traits contain users the buyer has not seen before. As a result, buyers may want these traits to add new users to their audience segments.
* **Enhance existing audiences:** High overlap suggests your traits contain users similar to those a buyer already knows about. As a result, buyers may want these traits to help make targeted, incremental improvements to developed audiences.
Price this use case as follows:

* Unit of Measure: Flat fee
* Price: Free ($0.00)
**Modeling** 

A **[!UICONTROL  Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [ algorithmic modeling](../../../c_features/c_models/understanding-models.md#concept_441E566718B845929880B0823A9ECA9F). Buyers look at the model results to find new audiences in your data that share similar conversion attributes to their own. Price this use case as follows: 
* Unit of Measure: Flat fee
* Price: Discounted or market rate price


**Activation** 

An **[!UICONTROL  Activation]** use case lets buyers send data to a[ destination](../../../c_features/c_destinations/c_destinations.md#concept_5BDA346C376C4B719EA394108AB2735A). With this use case, buyers cannot compare data with an overlap report or in an algorithmic model. Price this use case as follows: 

* Unit of Measure: CPM
* Price: CPM market rate

## Billing and Price Options {#section_FAD9EDF933A248D4B762DA1C5D4BF2EF}

The billing and price options control how buyers pay for your data. 



<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Billing Cycle</span> </td> 
   <td colname="col2"> <span class="uicontrol"> Monthly in Arrears</span> is the only option. The billing cycle ends on the 10th day of each month. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Unit of Measure</span> </td> 
   <td colname="col2">Charge data buyers on a CPM rate or flat fee. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D">
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> With CPM pricing, data buyers are required to self-report usage. </li>
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Wit flat fee pricing, data buyers do not report usage because they're charged a fixed rate. </li>
    </ul></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Price</span> </td> 
   <td colname="col2"> The amount a seller charges the buyer as CPM rate or flat fee price, in dollars. </td> 
  </tr> 
 </tbody> 
</table>


## Plan Notes {#section_1DC56D7CCD574C1BAB1ABA033842E1CA}

In the **[!UICONTROL  Additional Notes]** field, take some time to describe each data plan in a feed. A good, brief description helps buyers understand the content or purpose of each plan in a data feed. Buyers can read data feed and plan descriptions as they search for or evaluate new data sources. 
