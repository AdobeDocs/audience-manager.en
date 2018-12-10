---
description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price > 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price > 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Managing Trait Rules
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
index: y
internal: n
snippet: y
---

# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price > 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.

<!--
c_tb_rules.xml
-->

## Main Signal Rules Features Described

![](assets/manage-trait-rules.png)

1. The **[!UICONTROL Expression Builder]** or **[!UICONTROL Code View]** tabs provide an overview of the rules in your trait. The **[!UICONTROL Expression Builder]** tab lets you create rules with fields and drop-down menus. The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue".`

1. The fields and controls in this section let you create signals from key-value pairs and set the relationship between them with a comparison operator. A key, operator, and value are required.
1. The Data Explorer Options allow you to backfill trait realizations for your signals.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Contact your Adobe consultant for details.
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits. 
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Contact your Adobe consultant for details.
1. The test fields let you validate combinations of signal rules or the URLs that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#task_5A20AA9D87284DB49BE5D1DF0717F949}

Rules (or expressions) consist of individual or groups of key-value pairs. Comparison operators set the relationship between key-value pairs. To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!--
t_tb_create_rules.xml
-->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. Expand the **[!UICONTROL Trait Expression]** section and enter a key and value name. This creates a *`signal`*.

   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.

1. Select a [comparison operator](../../c-features/traits/trait-comparison-operators.md#concept_1A1761AA403341D7B91C0E26DC4294F4) from the **[!UICONTROL Operator]** dropdown. The comparison operator evaluates the relationship between the elements in a signal.

   >[!NOTE]
   >
   >The Boolean [!UICONTROL OR] operator establishes the relationship between multiple signals *within* a group and cannot be changed.

1. Click **[!UICONTROL Add Rule]**. The saved rule appears in the traits workspace above the data entry fields.

### Example {#example_23FEFF7C30884286946785DD33200062}

In the example below, a user has created a new trait rule based on the product ID. To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_LIKE_THIS]
>
>* [Create a New Rule Group](../../c-features/traits/manage-trait-rules.md#task_9BEF4C9F33504DB8B78A6C4E1C7D0A3D)
>* [Move Rules Between Groups](../../c-features/traits/manage-trait-rules.md#task_4225B7CB164C4ECFB30F1315C60EC4B3)
>* [Delete a Trait Rule](../../c-features/traits/manage-trait-rules.md#task_59C7044CC983478E979566BEC5F793A8)

## Create a New Rule Group {#task_9BEF4C9F33504DB8B78A6C4E1C7D0A3D}

This procedure describes how to create a new rule group.

<!--
t_tb_new_rule_group.xml
-->

Your trait must contain at least two rules before you can create a new rule group.

1. Move your cursor over the rule you want to move to highlight it.
1. Hover over the highlighted rule border.

   This automatically separates the rule from its current group and moves it into a new group.

   >[!NOTE]
   >
   >Drag a rule back to its original group if you move it unintentionally.

1. Select a Boolean operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_LIKE_THIS]
>
>* [Create a Trait Rule](../../c-features/traits/manage-trait-rules.md#task_5A20AA9D87284DB49BE5D1DF0717F949)
>* [Move Rules Between Groups](../../c-features/traits/manage-trait-rules.md#task_4225B7CB164C4ECFB30F1315C60EC4B3)
>* [Delete a Trait Rule](../../c-features/traits/manage-trait-rules.md#task_59C7044CC983478E979566BEC5F793A8)

## Move Rules Between Groups {#task_4225B7CB164C4ECFB30F1315C60EC4B3}

To move a rule, click and drag it to another group.

>[!MORE_LIKE_THIS]
>
>* [Create a Trait Rule](../../c-features/traits/manage-trait-rules.md#task_5A20AA9D87284DB49BE5D1DF0717F949)
>* [Create a New Rule Group](../../c-features/traits/manage-trait-rules.md#task_9BEF4C9F33504DB8B78A6C4E1C7D0A3D)
>* [Delete a Trait Rule](../../c-features/traits/manage-trait-rules.md#task_59C7044CC983478E979566BEC5F793A8)

## Edit a Trait {#task_F8858067BFEF47CB95C892B94CC39CD1}

This procedure describes how to edit a trait.

<!--
t_tb_edit.xml
-->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the trait you want to edit.

   This brings up the trait management icons. 1. Click the pencil to edit the trait.
   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#task_59C7044CC983478E979566BEC5F793A8}

This procedure describes how to delete a trait rule.

<!-- 
t_tb_delete_rule.xml
-->
1. In the [!UICONTROL Traits] dashboard, hover over the [!UICONTROL Actions] columns for the trait you want to edit and click the pencil icon. This brings up the trait management icons.
1. Expand the [!UICONTROL Trait Expression] section.
1. Hover over the rule you want to delete and click the X icon.
   Clicking X deletes the rule immediately.