---
description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Create or Update Trait Rules and Segment Rules
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
TQID: https://experienceleague.adobe.com/7vkYd55lKv1PCjRqX-OxK1A-VIjgH3O9Tx0AnbZvRWA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.

>[!IMPORTANT]
>
>The Bulk Management Tools are not an officially supported Adobe offering. Troubleshooting and support through Customer Care will be handled on a case by case basis.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

## Working with trait rules {#trait-rules}

In your worksheet, the trait rule column returns and accepts rules that consist of Boolean expressions, comparison operators, and regular expressions. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. Or, if you're familiar with rule syntax, you can write expressions directly in the worksheets.

## Rule builder example {#rule-builder-example}

Let's take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. However, this isn't a set of step-by-step instructions for those tools. Instead we're going to start with a simple rule that's already been created. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we've created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule. 

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. This will help prevent you from uploading an invalid rule.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. Before you start, be sure to read the documentation that covers things like operators, expression, and required variables. We recommend you review the following:

* [Working With Comparison Operators In Trait Builder](../../features/traits/trait-comparison-operators.md) 
* [Order of Operations](../../features/traits/trait-operator-precedence.md) 
* [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md) 
* [Sample Expressions With Boolean and Comparison Operators](../../features/traits/trait-expression-samples.md)
