---
description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager Predictive Audiences
---

# [!UICONTROL Predictive Audiences] Overview {#predictive-audiences}

[!UICONTROL Predictive Audiences] helps you classify an unknown audience into distinct personas, in real-time, using advanced data science techniques.

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

In a marketing context, a persona is an audience segment defined by visitors, users, or potential buyers, who share a specific set of traits, such as demographics, browsing habits, shopping history, etc.

[!UICONTROL Predictive Audiences] models take this concept a step further, by enabling you to use Audience Manager's machine learning capabilities to classify unknown audiences into distinct personas. Audience Manager helps you achieve this by calculating the propensity of your unknown first-party audience for a set of known first-party audiences.

When you create a [!UICONTROL Predictive Audiences] model, the first step is choosing the baseline traits or segments that you want your target audience to be classified by. These traits or segments will define your personas.

During the evaluation phase, the model creates a new [!UICONTROL Predictive Audiences] segment for each trait or segment that you defined as baseline. The next time Audience Manager sees a visitor from your target audience who is not classified for a persona  (did not qualify for any of your baseline traits or segments), the [!UICONTROL Predictive Audiences] model will determine which of the predictive segments the visitor should belong to, and add the visitor to that segment.

You can identify the predictive segments created by the model, in the [!UICONTROL Segments] page. Each [!UICONTROL Predictive Audiences] model has its own folder under the [!UICONTROL Predictive Audiences] folder, and you can see each model's segments by clicking the model folder.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Use Cases {#use-cases}

To help you better understand how and when you could use [!UICONTROL Predictive Audiences], here are a few use cases that Audience Manager customers can solve by using this feature.

### Use Case #1

As a marketer in an e-commerce company, I want to classify all my web and mobile visitors into various brand affinity categories, so that I can personalize their user experience.

### Use Case #2

As a marketer in a media company, I want to classify my unauthenticated web and mobile visitors by favorite genres, so that I can suggest to them personalized content across all channels.

### Use Case #3

As an advertiser for an airline company, I want to make sure I classify my audience based on their interest in travel destinations, so that I can advertise to them in real time, within a short retargeting window.

### Use Case #4

As an advertiser, I want to classify my first-party audience in real time, so that I can react quickly to trending news.

### Use Case #5

As a marketer, I want to predict which customer journey phase my website visitors are in, such as discovery, engagement, purchase or retention, so that I can target them accordingly.

### Use Case #6

As a media company, I want to categorize my audience, so that I can sell my advertising space at premium pricing, while offering my visitors relevant ads.

## How [!UICONTROL Predictive Audiences] Models Work {#how-predictive-audiences-models-work}

When you create a [!UICONTROL Predictive Audiences] model, you go through three steps:

1. First, you select a minimum of two traits or two segments that will define your personas.
1. Then, you choose a trait or segment that defines the target audience that you want to classify.
1. Finally, you choose a name for the model and select a data source that will store the predictive segments.

### Selection Criteria for Personas {#selection-personas}

You can choose any of your first-party traits or segments to define your personas. However, for optimal results, here's a set of recommended best practices:

* Choose your persona traits or segments so that each persona has at least a few hundred [device IDs](../../reference/ids-in-aam.md).
* If your traits are based on [cross-device IDs](../../reference/ids-in-aam.md), you can wrap them in segments with [Profile Merge Rules](../profile-merge-rules/merge-rules-overview.md) that use [device IDs](../../reference/ids-in-aam.md), such as [!UICONTROL Device Graph]. This will ensure there are enough [device IDs](../../reference/ids-in-aam.md) that the algorithm can learn from.
* We recommend choosing traits or simple segments for your perosnas, consisting of 1 to 3 traits.
* Choose baseline traits or segments which have minimal overlap.
* Make sure you are capturing granular traits across your digital properties.

### Selection Criteria for Target Audience {#selection-audience}

Similar to persona selection, you should choose your trait or segment that defines your target audience in such way that it has real time users with rich sets of traits, for classification into the right persona.

### [!UICONTROL Predictive Audiences] Model Training Phase {#model-training}

Before the algorithm can classify your first-party audience into the right personas, it needs to train itself on your data.

For each persona that you define, the algorithm analyzes its respective audience and evaluates any real time and/or onboarded trait activity for its users in the last 30 days.
This step takes place once every 24 hours, to account for changes in your first-party audience.

### [!UICONTROL Predictive Audiences] Model Classification Phase {#model-classification}

When a visitor who is part of the target audience is seen in real time, the model evaluates whether the visitor is part of the defined personas. For every visitor that does not belong to any of the personas, the model assigns a persona qualification score.

While evaluating first-party audiences and assigning scores, the model uses the default **[!UICONTROL Profile Merge Rule]** defined in your account. Finally, the visitor gets classified into the persona for which they received the highest score.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Considerations and Limitations {#considerations}

>[!IMPORTANT]
> Read through this section carefully before moving on to the implementation phase.

When configuring your [!UICONTROL Predictive Audiences] models, keep in mind the following considerations and limitations:

* You can create up to 10 [!UICONTROL Predictive Audiences] models.
* For each model, you can choose up to 50 base traits / segments.
* Second and third-party data are not currently supported in [!UICONTROL Predictive Audiences].
* Audience classification is done only for real time first-party audiences. Onboarded first-party audience classification may be supported in a future update.
  >[!IMPORTANT]
  > Currently, the [!UICONTROL Total Segment Population] of your predictive segments is displayed as 0, and [Batch Outbound Data Transfers](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) are not supported for [!UICONTROL Predictive Audiences]. This behavior will change in a future update.
* [!UICONTROL Predictive Audiences] performs audience classification based on your first party traits, from all your first-party data sources.
* Segment evaluation for [!UICONTROL Predictive Audiences] uses the default **[!UICONTROL Profile Merge Rule]** that you defined in your account. To learn more about [!UICONTROL Profile Merge Rules] see the dedicated [documentation](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html).
* Some traits and segments are not supported as baselines or target audiences. [!UICONTROL Predictive Audiences] models will fail to save when choosing one of the following as baselines or target audiences:
  * Predictive traits and segments created with predictive traits;
  * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) traits or segments;
  * Algorithmic traits;
  * Second and third-party traits.

## [!UICONTROL Data Export Controls] {#dec}

Predictive segments created by [!UICONTROL Predictive Audiences] models inherit the [Data Export Controls](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) from the following first-party data sources:

1. The first-party data source that you choose when building the model.
1. The first-party data sources of your target audience. Specifically, the data export controls of the traits or segments that make up your target audience.

The newly created predictive traits and segments will have the same privacy restrictions as the union of the first-party data sources described above.

Traits that have additional restrictions that aren’t part of the [!UICONTROL Predictive Audiences] segment privacy restrictions will be excluded from the training phase, and will not become influential for the model.

## [!UICONTROL Role-Based Access Controls] {#rbac}

The traits and segments that you choose for personas and audience classification are subject to Audience Manager [Role-Based Access Controls](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager users can only select traits or segments for personas and target audiences, that they have [permission to view](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
