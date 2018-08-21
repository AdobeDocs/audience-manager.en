---
description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Sample Expressions With Boolean and Comparison Operators
uuid: 94413c7b-4f56-4184-addf-de93be99fe72
index: y
internal: n
snippet: y
translate: y
---

# Sample Expressions With Boolean and Comparison Operators


## Code Samples Overview {#section_046415174EF84FDAA6E3C92649BFB0F3}

Create your own trait rules with the Expression Builder code editor. The following examples can help you get started. Some of the examples preface the *` key`* variable with ` c_` to identify it as a user-defined variable. Include the ` c_` prefix (or any other naming convention) for *` key`* variable if your event calls send data to Audience Management using that syntax. 

## Boolean Expressions {#section_294C03461BE44795A507BF9A65808CCA}

**AND Example** 

The rule establishes trait qualification requirements using Boolean AND operators. 

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

**OR Example** 

This rule establishes trait qualification requirements using Boolean OR and AND operators. 

|  Sample code  | To qualify, a visitor must  |
|---|---|
| 
```
(a== "1" OR b=="1") AND (c== "new")
```
| Meet the conditions set by variables *` a`* or *` b`* and *` c`*.  |

**Range Example with Greater Than, Less Than, Equal To** 

This rule establishes trait qualification requirements using a range. 

|  Sample code  | To qualify, a visitor must  |
|---|---|
| 
```
(price>= 1.00 AND price<= 100.00)
```
| Meet any price condition between 1.00 and 100.00.  |

