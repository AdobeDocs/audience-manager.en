---
description: Use logical operators to group key-value pairs and backfill traits.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Supported Logical Operators
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
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