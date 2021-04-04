---
description: This article describes the comparison operators used by Trait Builder.
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: Working with Comparison Operators in Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
---
# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## Purpose of Comparison Operators

<!-- c_tb_comparison_operators.xml -->

Comparison operators (or relational operators) are used to compare, test, or evaluate the relationship between different values. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. For example, you could create a signal rule to define an audience for expensive camera shoppers. In this case, you could create a camera/price key-value pair and qualify a user if they've looked for a camera with a price equal to or greater than a set amount.

## Advantages of Comparison Operators

Comparison operators are useful when you need to evaluate and create traits based on multiple values. Looking at prices on goods and services can illustrate this condition. For example, your business may want to identify visitors based on the prices of the products they view. However, it can be administratively inefficient to define individual segments based on specific values. Comparison operators help overcome this hurdle by establishing segmentation triggers based on price thresholds or ranges.

## Comparison Operators

You can build rules with the following comparison operators:  

|  Operator  | Definition  |
|---|---|
| **==** | Equal to  |
| **!=** | Not equal to  |
| **>** | Greater than  |
| **<** | Less than  |
| **=>** | Greater than/equal to  |
| **<=** | Less than/equal to  |

## Named Operators

You can build rules with the following named operators:  

|  Operator  | Evaluates to [!DNL True] When  |
|---|---|
| **[!UICONTROL Contains]** |The value in a key-value pair *contains* characters specified by this operator.  |
| **[!UICONTROL Matcheswords]** |The value in a key-value pair *matches* the pattern specified by this operator.  |
| **[!UICONTROL Startswith]** |The value in a key-value pair *starts with* characters specified by this operator.  |
| **[!UICONTROL Endswith]** |The value in a key-value pair *ends with* the characters specified by this operator.  |
| **[!UICONTROL Matchesregex]** |The value in a key-value pair *matches* the pattern specified by a regular expression. [Learn more](../../features/traits/trait-builder-regex.md) about using regular expressions in [!UICONTROL Trait Builder].  |

>[!MORELIKETHIS]
>
>* [Boolean Expressions in Trait and Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Understanding Boolean Expressions in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Order of Operations in TraitBuilder Expressions](../../features/traits/trait-operator-precedence.md)
>* [Sample Expressions With Boolean and Comparison Operators](../../features/traits/trait-expression-samples.md)
