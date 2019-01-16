---
description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Create or Update Trait Rules and Segment Rules
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
---

# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [Audience Manager APIs](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_api.html) instead. [RBAC group permissions](../../features/administration/administration-overview.md) assigned in the Audience Manager UI are honored in the Bulk Management Tools.

## Working with trait rules {#section_D0E125BEC35E40AEA410725C364CEF8E}

In your worksheet, the trait rule column returns and accepts rules that consist of Boolean expressions, comparison operators, and regular expressions. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. Or, if you're familiar with rule syntax, you can write expressions directly in the worksheets.

## Rule builder example {#section_F4E7928A68FA41708B8C29525689A80C}

Let's take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. However, this isn't a set of step-by-step instructions for those tools. Instead we're going to start with a simple rule that's already been created. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md#concept_FABA1F399CFD4E83B874043638D0FA54) and [Trait Builder](../../features/traits/about-trait-builder.md#concept_BCDC4BCAEB4A4879AFA4A9B98D9ED369).

With the visual rule builder, we've created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule. 

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. This will help prevent you from uploading an invalid rule.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#section_62D0280B95E644B4B92D6AC5387FBD5F}

You can write your own rules outside of [!UICONTROL Rule Builder]. Before you start, be sure to read the documentation that covers things like operators, expression, and required variables. We recommend you review the following:

* [Working With Comparison Operators In Trait Builder](../../features/traits/trait-comparison-operators.md) 
* [Order of Operations](../../features/traits/trait-operator-precedence.md) 
* [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md) 
* [Sample Expressions With Boolean and Comparison Operators](../../features/traits/trait-expression-samples.md)

