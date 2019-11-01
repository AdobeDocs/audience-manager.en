---
description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Boolean Expressions in Trait and Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
---

# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.

<!-- 

c_tb_boolean.xml

 -->

**Boolean Expressions**

Boolean logic is a branch of algebra that uses a few basic expressions (or operators) to determine if a statement is true or false. The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. Combinations of these expressions help you make focused trait or segment qualification rules uniquely suited to your data requirements. The following illustration shows how basic Boolean expressions work.

<br>&nbsp;

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>The [!UICONTROL NOT] operator uses an implied "and" condition and is sometimes written as [!UICONTROL AND NOT].

**How to Use Boolean Expressions in Trait and Segment Builder**

You build trait and segment qualification rules with Boolean expressions. The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].  

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
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>Narrow, focused audience qualification requirements. </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Broad, less focused audience qualification requirements. </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Narrow, focused audience qualification requirements. </p> <p>Useful when there are multiple conditions that make defining audience qualification requirements difficult or inefficient. Occasionally, it is easier to validate against requirements that exclude rather than include. </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND] Use Case Example**

The [!UICONTROL AND] operator is useful when you have easily enumerated trait membership requirements. For example, say you need to create an audience of “expensive camera shoppers.” With a pixel model, you would have to create and place pixels for cameras and a numeric price value on your page. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). The result is efficient data collection with fewer HTTP calls, which, in turn, helps preserve the user experience on your site.

**[!UICONTROL OR] Use Case Example**

The [!UICONTROL OR] operator is useful when you want to create signals with broad audience qualification requirements. If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] may be most useful when you want to rapidly create a broad audience of qualified site visitors.

**[!UICONTROL AND NOT] Use Case Example**

The [!UICONTROL AND NOT] operator is useful when it’s easier to define an audience by *exclusion* rather than *inclusion*. For example, say you're having a sale and want to segment visitors into customers who look at full price items only. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. This is administratively efficient because you usually have fewer sale price items compared to those offered at full price. With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals). 

>[!MORELIKETHIS]
>
>* [Working with Comparison Operators in TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Order of Operations in TraitBuilder Expressions](../features/traits/trait-operator-precedence.md)
