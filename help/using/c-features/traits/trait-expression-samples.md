---
description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Sample Expressions With Boolean and Comparison Operators
uuid: ee74c376-2099-4816-8694-43f58845a0ac
index: y
internal: n
snippet: y
---

# Sample Expressions With Boolean and Comparison Operators {#sample-expressions-with-boolean-and-comparison-operators}

Examples you can refer to for creating expressions in the [!UICONTROL Expression Builder] code editor.

## Code Samples Overview {#section_046415174EF84FDAA6E3C92649BFB0F3}

<!-- 

r_tb_expression_samples.xml

 -->

Create your own trait rules with the [!UICONTROL Expression Builder] code editor. The following examples can help you get started. Some of the examples preface the *`key`* variable with `c_` to identify it as a user-defined variable. Include the `c_` prefix (or any other naming convention) for *`key`* variable if your event calls send data to [!DNL Audience Manager] using that syntax.

## Boolean Expressions {#section_294C03461BE44795A507BF9A65808CCA}

### [!UICONTROL AND] Example

The rule establishes trait qualification requirements using Boolean [!UICONTROL AND] operators.  

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sample Code </th> 
   <th colname="col2" class="entry"> To qualify, a visitor must </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <codeblock>
      (c_make=="A")&amp;nbsp;AND&amp;nbsp;(c_model=="B")&amp;nbsp;AND&amp;nbsp;(c_search=="1") 
    </codeblock> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Look for a specific make and model. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Find the product from a search results page (search = "1" or "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL OR] Example

This rule establishes trait qualification requirements using Boolean [!UICONTROL OR] and [!UICONTROL AND] operators.  

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sample code </th> 
   <th colname="col2" class="entry"> To qualify, a visitor must </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <codeblock>
      (a==&amp;nbsp;"1"&amp;nbsp;OR&amp;nbsp;b=="1")&amp;nbsp;AND&amp;nbsp;(c==&amp;nbsp;"new") 
    </codeblock> </td> 
   <td colname="col2"> Meet the conditions set by variables <span class="varname"> a </span> or <span class="varname"> b </span> and <span class="varname"> c </span>. </td> 
  </tr> 
 </tbody> 
</table>

## Range Example with Greater Than, Less Than, Equal To

This rule establishes trait qualification requirements using a range.  

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sample code </th> 
   <th colname="col2" class="entry"> To qualify, a visitor must </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <codeblock>
      (price&gt;=&amp;nbsp;1.00&amp;nbsp;AND&amp;nbsp;price&lt;=&amp;nbsp;100.00) 
    </codeblock> </td> 
   <td colname="col2" valign="middle" align="left"> Meet any price condition between 1.00 and 100.00. </td> 
  </tr> 
 </tbody> 
</table>