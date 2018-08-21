---
description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Boolean Expressions in Trait and Segment Builder
uuid: 5304074a-9aab-4dea-a31c-12e4babcd410
index: y
internal: n
snippet: y
translate: y
---

# Boolean Expressions in Trait and Segment Builder

**Boolean Expressions** 

Boolean logic is a branch of algebra that uses a few basic expressions (or operators) to determine if a statement is true or false. The most common operators are AND, OR, and NOT. Combinations of these expressions help you make focused trait or segment qualification rules uniquely suited to your data requirements. The following illustration shows how basic Boolean expressions work. 

![](assets/BooleanOverview_small.png) 
>[!NOTE]
>
>The NOT operator uses an implied "and" condition and is sometimes written as AND NOT.



**How to Use Boolean Expressions in Trait and Segment Builder** 

You build trait and segment qualification rules with Boolean expressions. The table below describes general best practices for creating qualification criteria with AND, OR, and NOT. 

<table id="table_C762872C98F54C4A86A2F1C840A86657">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Expression </th>
   <th colname="col2" class="entry"> Use it to create </th>
   <th colname="col3" class="entry"> To qualify </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"><p><b>AND</b></p></td>
   <td colname="col2"><p>Narrow, focused audience qualification requirements. </p></td>
   <td colname="col3"><p>Users <i>must</i> belong to all specified traits or segments. </p></td>
  </tr>
  <tr>
   <td colname="col1"><p><b>OR</b></p></td>
   <td colname="col2"><p>Broad, less focused audience qualification requirements. </p></td>
   <td colname="col3"><p>Users <i>can</i> belong to any specified traits or segments. </p></td>
  </tr>
  <tr>
   <td colname="col1"><p><b> NOT</b></p></td>
   <td colname="col2"><p>Narrow, focused audience qualification requirements. </p><p>Useful when there are multiple conditions that make defining audience qualification requirements difficult or inefficient. Occasionally, it is easier to validate against requirements that exclude rather than include. </p></td>
   <td colname="col3"><p>Users <i>must not</i> belong to an excluded trait or segment. </p></td>
  </tr>
 </tbody>
</table>

**AND Use Case Example** 

The AND operator is useful when you have easily enumerated trait membership requirements. For example, say you need to create an audience of “expensive camera shoppers.” With a pixel model, you would have to create and place pixels for cameras and a numeric price value on your page. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras AND price). The result is efficient data collection with fewer HTTP calls, which, in turn, helps preserve the user experience on your site. 

**OR Use Case Example** 

The OR operator is useful when you want to create signals with broad audience qualification requirements. If you have several trait or segment qualification requirements, the OR operator will evaluate to true when your site visitors exhibit *any* of those characteristics. OR may be most useful when you want to rapidly create a broad audience of qualified site visitors. 

**AND NOT Use Case Example** 

The AND NOT operator is useful when it’s easier to define an audience by *exclusion* rather than *inclusion*. For example, say you're having a sale and want to segment visitors into customers who look at full price items only. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier qualify visitors if they have *not* seen a sale price item. This is administratively efficient because you usually have fewer sale price items compared to those offered at full price. With a Boolean NOT, visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, AND NOT is the opposite of the AND use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals). 
>[!MORE_LIKE_THIS]
>
>* [ Working with Comparison Operators in TraitBuilder ](c_tb_comparison_operators.md#concept_1A1761AA403341D7B91C0E26DC4294F4)
>* [ Order of Operations in TraitBuilder Expressions ](c_tb_operator_precedence.md#concept_F8A8B8B8E4814A86B34493B104D44464)
