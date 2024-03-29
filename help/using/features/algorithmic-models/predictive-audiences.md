---
description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
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
1. Finally, you choose a name for the model, a data source that will store the predictive segments, and a [!UICONTROL Profile Merge Rule] for the model.

### Selection Criteria for Personas {#selection-personas}

You can choose any of your first-party traits or segments to define your personas. However, for optimal results, here's a set of recommended best practices:

* Choose your persona traits or segments so that each persona has at least a few hundred [device IDs](../../reference/ids-in-aam.md).
* If your traits are based on [cross-device IDs](../../reference/ids-in-aam.md), you can wrap them in segments with [Profile Merge Rules](../profile-merge-rules/merge-rules-overview.md) that use [device IDs](../../reference/ids-in-aam.md), such as [!UICONTROL Device Graph]. This will ensure there are enough [device IDs](../../reference/ids-in-aam.md) that the algorithm can learn from.
* We recommend choosing traits or simple segments for your personas, consisting of 1 to 3 traits.
* Choose baseline traits or segments which have minimal overlap.
* Make sure you are capturing granular traits across your digital properties.

### Selection Criteria for Target Audience {#selection-audience}

Depending on your use case, whether you want to classify users in real-time, in batch, or both, choose a target audience ([!UICONTROL trait] or [!UICONTROL segment]) which has a significant real-time and/or total population. Similar to persona selection, we recommend that your target audience [!UICONTROL trait] or [!UICONTROL segment] has users with rich profiles (rich sets of [!UICONTROL traits]).

When selecting the target audience, analyze your your use case and decide which types of IDs you want to classify: [!UICONTROL device IDs] or [!UICONTROL cross-device IDs]. The [!UICONTROL Profile Merge Rule] that you select when creating the model defines the data that will be used to place each user into the predictive [!UICONTROL segments].

As a best practice, we recommend choosing a [!UICONTROL Profile Merge Rule] that has the same configuration as your target audience [!UICONTROL Profile Merge Rule], or one that includes the profile type (device profile or authenticated profile) of your target audience.

### [!UICONTROL Predictive Audiences] Model Training Phase {#model-training}

Before the algorithm can classify your first-party audience into the right personas, it needs to train itself on your data.

For each persona that you define, the algorithm analyzes its respective audience and evaluates any real time and/or onboarded trait activity for its users in the last 30 days.
This step takes place once every 24 hours, to account for changes in your first-party audience.

### [!UICONTROL Predictive Audiences] Model Classification Phase {#model-classification}

For real-time and batch audience classification, the model first checks whether a user belongs to the target audience. If the user qualifies for the target audience and does not belong to any of the personas, the model assigns them a persona qualification score.

While evaluating first-party audiences and assigning scores, the model uses the default **[!UICONTROL Profile Merge Rule]** defined in your account. Finally, the visitor gets classified into the persona for which they received the highest score.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Considerations and Limitations {#considerations}

>[!IMPORTANT]
> Read through this section carefully before moving on to the implementation phase.

When configuring your [!UICONTROL Predictive Audiences] models, keep in mind the following considerations and limitations:

* You can create up to 10 [!UICONTROL Predictive Audiences] models.
* For each model, you can choose up to 50 base traits / segments.
* Second and third-party data are not currently supported in [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] performs audience classification based on your first party traits, from all your first-party data sources.
* Segment evaluation for [!UICONTROL Predictive Audiences] uses the **[!UICONTROL Profile Merge Rule]** that you choose during model creation. To learn more about [!UICONTROL Profile Merge Rules] see the dedicated [documentation](../profile-merge-rules/merge-rules-overview.md).
* Some traits and segments are not supported as baselines or target audiences. [!UICONTROL Predictive Audiences] models will fail to save when choosing one of the following as baselines or target audiences:
  * Predictive traits and segments created with predictive traits;
  * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) traits or segments;
  * Algorithmic traits;
  * Second and third-party traits.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] cannot be used in [!UICONTROL Audience Lab]. 

## [!UICONTROL Data Export Controls] {#dec}

Predictive segments created by [!UICONTROL Predictive Audiences] models inherit the [Data Export Controls](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) from the following first-party data sources:

1. The first-party data source that you choose when building the model.
1. The first-party data sources of your target audience. Specifically, the data export controls of the [!UICONTROL traits] or [!UICONTROL segments] that make up your target audience.
1. The [Data Export Controls](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) of the [!UICONTROL Profile Merge Rule] that you selected for the model.

The newly created predictive [!UICONTROL traits] and [!UICONTROL segments] will have the same privacy restrictions as the union of the first-party data sources described above.

Traits that have additional restrictions that aren’t part of the [!UICONTROL Predictive Audiences] segment privacy restrictions will be excluded from the training phase, and will not become influential for the model.

## [!UICONTROL Profile Merge Rules] {#pmr} 

All predictive segments will be assigned the [!UICONTROL Profile Merge Rule] that you selected when creating the model. The [!UICONTROL Profile Merge Rule] that you choose is important for the following reasons:

* It defines which devices and/or authenticated profiles should be taken into account when the model analyzes the influential [!UICONTROL traits], at the time of classifying a user into a predictive [!UICONTROL segment].
* It governs which [!UICONTROL trait] types (device level or cross-device level) should be used during the model training step and surfaced as influential [!UICONTROL traits]. Predictive [!UICONTROL segments] are subsets of your target audience.
  * If the target audience is a segment, we recommend that you select the same [!UICONTROL Profile Merge Rule] for the model as the one assigned to your target audience, or a [!UICONTROL Profile Merge Rule] that includes the profile type of your target audience.
  * If the target audience is a [!UICONTROL trait], we recommend that you select a [!UICONTROL Profile Merge Rule] that can access the same type of data as the target audience trait (either device profile data or cross-device profile data).
* [!UICONTROL Profile Merge Rules] using the [!UICONTROL Current Authenticated Profiles] and [!UICONTROL No Device Profile] options are only supported for real-time audience classification. For more information see [Profile Merge Rules Options Defined](../profile-merge-rules/merge-rule-definitions.md).

Selecting a [!UICONTROL Profile Merge Rule] that uses both device data and cross-device  data maximizes the number of [!UICONTROL traits] that could be used for model training and user classification into the predictive [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

The traits and segments that you choose for personas and audience classification are subject to Audience Manager [Role-Based Access Controls](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager users can only select traits or segments for personas and target audiences, that they have [permission to view](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
