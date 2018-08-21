---
description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Order of Operations in Trait Builder
uuid: 2dd0a8ca-82c4-4d03-925b-c15fd3ec69cc
index: y
internal: n
snippet: y
translate: y
---

# Order of Operations in Trait Builder





<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operator precedence </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Comments </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parenthesis </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Expressions in parenthesis are always evaluated first and follow precedence order. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comparison operators </td> 
   <td colname="col2"> &amp;lt; &amp;gt; &amp;lt;= &amp;gt;= </td> 
   <td colname="col3"> Less than, greater than, less than/equal to, greater than/equal to are evaluated next. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Equality operators </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Equal to, not equal to are evaluated after the previous operators. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Boolean AND </td> 
   <td colname="col2"> AND </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Boolean OR </td> 
   <td colname="col2"> OR </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ Working with Boolean Expressions (AND, OR, NOT) in TraitBuilder ](c_tb_boolean.md#concept_B7537516B5D04CEBB9CFB4F4B780630F)
>* [ Working with Comparison Operators in TraitBuilder ](c_tb_comparison_operators.md#concept_1A1761AA403341D7B91C0E26DC4294F4)
