---
description: Use logical operators to group key-value pairs and backfill traits.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Supported Logical Operators
uuid: 0e6fbd6c-e32d-4eea-9c79-194f6d85c801
index: y
internal: n
snippet: y
---

# Supported Logical Operators{#supported-logical-operators}

Use logical operators to group key-value pairs and backfill traits.

## Supported Operators for Signal Search {#section_694E53CA51144359B9777C70B4347181}

Use the following supported logical operators to search for key-value pairs:

**Comparison Operators**

|  Operator  | Definition  |
|---|---|
| **==** | Equal to  |
| **>** | Greater than  |
| **<** | Less than  |
| **=>** | Greater than/equal to  |
| **<=** | Less than/equal to  |

**Named Operators**

|  Operator  | Evaluates to True When  |
|---|---|
| **Contains** |The value in a key-value pair *contains* characters specified by this operator.  |
| **Startswith** |The value in a key-value pair *starts with* characters specified by this operator.  |
| **Endswith** |The value in a key-value pair *ends with* the characters specified by this operator.  |

## Supported Operators for Trait Backfilling and Estimation {#section_93A79D83DE3F44FDA37E9707625DBDAF}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.

<!-- 

<p>The following operators, available in <a> Trait Builder</a>, are not supported for trait backfilling and estimation: </p> 
<p> 
 <ul id="ul_E9288AA1B00D448D908503CF9A6B4CE7"> 
  <li id="li_54DDBFDB221649E88079E1ED7BE1BB05"><span class="codeph"> !=</span> </li> 
  <li id="li_D4DD9F3A225D4F6EA2D1E6A655540E82"><span class="codeph"> matchesregex</span> </li> 
  <li id="li_4224BC6A9D37462EB43750653232C9F8"><span class="codeph"> matcheswords</span> </li> 
 </ul> </p>

 -->

>[!MORE_LIKE_THIS]
>
>* Link
