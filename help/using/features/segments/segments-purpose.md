---
description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Segments  Purpose, Composition, and Rules
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
---

# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes [!UICONTROL segments], their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## Purpose of [!UICONTROL Segments]

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. In Audience Manager, you create [!UICONTROL segments] with server-side rules. These rules let you build audience groups based on site visitor attributes such as:

* Behavior;
* Demographics (age, gender, income, etc.);
* Other characteristics you can define in the user interface.

## [!UICONTROL Segment] Composition

An Audience Manager [!UICONTROL segment] is a server-side rule that consists of individual or groups of traits. Traits are composed of data elements called key-value pairs. Along with rules you set at the [!UICONTROL segment] level, these key-value pairs contain the criteria that qualify visitors for trait and [!UICONTROL segment] membership.

## Considerations on [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Mapping

When mapping Adobe Analytics [!UICONTROL segments] or report suites to your Experience Cloud organization, Audience Manager automatically creates new, corresponding, read-only [!UICONTROL segments] and traits. You cannot edit or change the storage location of these [!UICONTROL segments] from Audience Manager. However, any change that you perform on your mapped Adobe Analytics [!UICONTROL segments] or report suites reflects in Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] are different from [!DNL Adobe Analytics] [!UICONTROL segments]. Read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.

## Create Rules-based [!UICONTROL Segments] With [!UICONTROL Segment Builder]

Unlike traditional pixels that fire in response to simple yes/no conditions, [!UICONTROL Segment Builder] lets you create complex [!UICONTROL segment] requirements. Like [!UICONTROL traits], [!UICONTROL segments] evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. These features help create focused audience [!UICONTROL segments] relevant to your business needs.

## Benefits

[!UICONTROL Segments] improve upon standard pixel-based audience creation/segmentation processes because they let you:

* Build relevant, useful [!UICONTROL segments] with first and third-party traits.
* Create sophisticated and complex segmentation rules with Boolean operators, comparison expressions, and recency/frequency criteria.
* Send [!UICONTROL segment] data to a destination partner.
* Monitor performance with Audience Manager reports.

>[!MORELIKETHIS]
>
>* [Signals, Traits, and Segments](../../reference/signal-trait-segment.md)
