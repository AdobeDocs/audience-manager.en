---
description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Trait Details Page
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
---

# Trait Details Page {#trait-details-page}

The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## Basic Information {#basics}

The [!UICONTROL Basic Information] section shows details about required and optional fields you completed when building the trait. This includes things like the trait type, trait ID, description, data source, and other metadata. These details vary depending on trait type (folder, onboarded, or rule-based).

![](assets/basicInfo.png)

## Trait Graph {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected trait. Hold your cursor over a trend line to see additional data for the selected trait.

[!UICONTROL Unique Trait Realizations] represent a count of unique users that added this trait to their profile over the given time range. The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* For rule-based traits, trait qualification happens in real-time, as users qualify for a trait in their browser.
* For onboarded traits, trait qualification happens after an inbound file is processed, i.e. the inbound file is [fed into Audience Manager](../../faq/faq-inbound-data-ingestion.md) and that is when the trait qualification happens.
* **Unique Trait Realizations**: A count of unique users that added this trait to their profile over the given time range.
* **Total Trait Population**: The number of unique users currently qualified for this trait.

    ![trait-graph](assets/trait-summary.png)

* **Identity Type Breakdown**: The first three entries show the top three cross-device data sources with the highest population count that have qualified for the trait, in descending order. The fourth entry shows the sum of all the other [!DNL DPUUIDs] ([!DNL CRM IDs]) that qualified for the trait, from the cross-device data sources that are not in the top three. This report appears only if you select Cross-device ID in the [!UICONTROL Show Results By] drop-down menu at the top right side of the page. The default drop-down option is [!UICONTROL Device ID], where this report is not displayed.

    ![trait-graph](assets/trait-identity.png)


## Trait Expression {#trait-expression}

The [!UICONTROL Trait Expression] section shows you the criteria users must meet to qualify for the trait. These rules are set when you [create or edit a trait](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

The [!UICONTROL Segments with this Trait] section lists all the segments the selected trait belongs to. You can click on a segment name to see details about that segment.

![](assets/traitSegments.png)

## Trait Audit/History Log {#trait-audit-history}

For rule-based and onboarded traits, the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to trait expression rules and who made them. If your trait has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. The audit log is not available for folder or algorithmic traits.

>[!NOTE]
>
>[!UICONTROL Not Available] in the [!UICONTROL By User] column means the account for that user has been deleted.

![](assets/traitHistory.png)