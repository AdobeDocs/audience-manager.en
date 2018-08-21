---
description: Describes how you can compare segments and traits to derive meaningful information from the results.
seo-description: Describes how you can compare segments and traits to derive meaningful information from the results.
seo-title: Comparing Segments to Traits
solution: Audience Manager
title: Comparing Segments to Traits
uuid: 2aa38244-e21e-412a-ac09-7cc40fe72518
index: y
internal: n
snippet: y
translate: y
---

# Comparing Segments to Traits

**Comparing Trait and Segment Uniques: An Example** 

At first glance, it may seem illogical to compare segments to traits and attempt to draw conclusions from the results. After all, segments and traits are different, so how can data derived from disparate items have meaning? However, in this case, we're not comparing traits and segments, but the number of unique visitors shared between them. The shared unique visitor count provides the common value that makes a segment to trait comparison possible. 

The following diagram illustrates the relationship between a trait and the segment it belongs to. In this case, we have a trait with 10 visitors and a segment with 1,000 visitors. They share 3 unique visitors in common. 

![](assets/s2t.png) 

The unique visitor count is the common, constant value shared between these different classes of objects. As a result, you can determine the unique visitor relationship between them as follows: 
* The trait shares 30% of its unique visitors with the segment (3/10 = 0.30).
* The segment shares 0.3% of its unique visitors with the trait (3/1,000 = 0.003)


**Find Value in Segment to Trait Comparisons** 

Looking at the overlap between traits and segments can help you estimate the total available visitor pool (forecasting) or find inefficient segments with too much overlap. 

<table id="table_5B211EF95216426299EB20253A5A9C1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Use Case </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"><b>Forecasting</b></td>
   <td colname="col2"><p>To determine the available visitor pool, sum the difference between the trait total (less overlap) and the segment total (less overlap). </p><p>This segment-trait combination could reach up to 1004 new users. </p></td>
  </tr>
  <tr>
   <td colname="col1"><b>Find Inefficient Segments</b></td>
   <td colname="col2"><p>If a trait is part of an AND group in a segment definition, the unique visitors who have that trait are already in the segment and not available for adding to the segment. You can use this report to find relevant traits with low overlap and add them to the segment definition, therefore increasing the reach of that segment audience pool. </p></td>
  </tr>
 </tbody>
</table>

