---
description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Segments  Purpose, Composition, and Rules
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
---

# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## Purpose of Segments

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. In Audience Manager, you create segments with server-side rules. These rules let you build audience groups based on site visitor attributes such as:

* Behavior;
* Demographics (age, gender, income, etc.);
* Other characteristics you can define in the user interface.

## Segment Composition

An Audience Manager segment is a server-side rule that consists of individual or groups of traits. Traits are composed of data elements called key-value pairs. Along with rules you set at the segment level, these key-value pairs contain the criteria that qualify visitors for trait and segment membership.

## Considerations on Adobe Analytics Segment Mapping

When mapping Adobe Analytics segments or report suites to your Experience Cloud organization, Audience Manager automatically creates new, corresponding, read-only segments and traits. You cannot edit or change the storage location of these segments from Audience Manager. However, any change that you perform on your mapped Adobe Analytics segments or report suites reflects in Audience Manager.

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## Create Rules-based Segments With Segment Builder

Unlike traditional pixels that fire in response to simple yes/no conditions, Segment Builder lets you create complex segment requirements. Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. These features help create focused audience segments relevant to your business needs.

## Benefits

Segments improve upon standard pixel-based audience creation/segmentation processes because they let you:

* Build relevant, useful segments with first and third-party traits.
* Create sophisticated and complex segmentation rules with Boolean operators, comparison expressions, and recency/frequency criteria.
* Send segment data to a destination partner.
* Monitor performance with Audience Manager reports.

>[!MORE_LIKE_THIS]
>
>* [Signals, Traits, and Segments](../../reference/signal-trait-segment.md)
