---
description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Predictive Audiences FAQ
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
---
# Predictive Audiences FAQ

Frequently asked questions about [!UICONTROL Predictive Audiences].

&nbsp;

**When should I use [!UICONTROL Predictive Audiences] as opposed to [!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] and [!UICONTROL Look-alike modeling] serve different use cases. The main differences between the two algorithms are these:

1. [!UICONTROL Look-alike modeling] takes a small audience as input and expands it. [!UICONTROL Predictive Audiences] takes a large audience as input, and divides it into smaller distinct audiences, defined by your personas.
1. The number of base segments is different for each algorithm. [!UICONTROL Predictive Audiences] requires at least two baselines, while [!UICONTROL Look-alike modeling] uses one baseline at most.
1. [!UICONTROL Predictive Audiences] performs real-time segment evaluation, while [!UICONTROL Look-alike modeling] does not.

Based on your use case, you should decide which model will be more relevant to you.

You can think of building a [!UICONTROL Predictive Audiences] model with a number of baselines as being the equivalent of building the same number of look-alike models, only without the real-time evaluation, and with a very high likelihood to have visitors belonging to multiple different personas, instead of one distinct persona.

&nbsp;

**How many personas/models am I allowed to create?**

You can create up to 10 [!UICONTROL Predictive Audiences] models. For each model, you can define up to 50 baseline traits or segments.

&nbsp;

**How can I build new segments from a [!UICONTROL Predictive Audiences] segment?**

Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**, and click the **[!UICONTROL Predictive Audiences]** folder. Find the desired segment, duplicate it, and edit it according to your needs.

&nbsp;

**When can I see the first results produced by my model?**

[!UICONTROL Predictive Audiences] model results are available within 24 hours from model creation, if the model runs successfully.

In case the model does not produce results within 24 hours, please reach out to your Adobe representative.

&nbsp;

**Why is my model not producing results or showing the Warning status?**

[!UICONTROL Predictive Audiences] models can fail to produce results due to a number of reasons:

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. The target audience trait / segment does not have any active or onboarded users.
1. The target audience users that were active or onboarded within the past 30 days do not have enough data in their user profiles (not enough traits to analyze).
1. The target audience segment uses a different [!UICONTROL Profile Merge Rule] from the one you chose for the model.
1. The data source of your target audience traits may not be included in the [!UICONTROL Profile Merge Rule] that you chose for the model.

For optimal results, follow the suggested guidelines from [Selection Criteria for Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) and [Selection Criteria for Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

&nbsp;

**Why is my model showing the [!UICONTROL Error] status?**

The model failed to run. In such cases, please reach out to your [!DNL Adobe] representative.

&nbsp;

**How can I change the [!UICONTROL Profile Merge Rule] for a [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Create a new model by selecting the same personas and target audience as your previous model. During model creation, assign a different [!UICONTROL Profile Merge Rule].

>[!WARNING]
> Alternatively, you can use [Segment Builder](../features/segments/segment-builder.md) to manually create a [!UICONTROL segment] with an existing predictive [!UICONTROL trait] and assign it a [!UICONTROL Profile Merge Rule] of your choice.
> 
> However, we do not recommend this practice, since predictive [!UICONTROL traits] automatically inherit the [!UICONTROL Profile Merge Rule] of the model they belong to, and they are built from influential [!UICONTROL traits] that comply with the [!UICONTROL Profile Merge Rule] of the model.

&nbsp;

**What [!UICONTROL Profile Merge Rule] should I choose?**

When choosing the [!UICONTROL Profile Merge Rule] for your model, analyze your use case closely.

Let's say your target audience [!UICONTROL segment] uses a [!UICONTROL Profile Merge Rule] based on authenticated profiles + [!DNL Device Graph] profiles, and you select the same [!UICONTROL Profile Merge Rule] for the predictive [!UICONTROL segments]. In this case, both device level and cross-device level [!UICONTROL traits] will be used in training the model and in the placement of the user into a predictive [!UICONTROL segment].

If, however, you select a [!UICONTROL Profile Merge Rule] based only on device profiles, none of your cross-device [!UICONTROL traits] will become influential and will not contribute to the placement of users into a predictive [!UICONTROL segment]. This may adversely affect the model accuracy and reach.

Analyze your use case carefully and decide which [!UICONTROL trait] types you want the model to learn from and what type of data you want the model to use for classification.

**Could a user from the target audience who isn't part of any persona trait / segment not be classified?**

Yes, in case the user does not have any traits in his profile. In that case, the user will get a match score of 0 to all of the persona traits / segments, and therefore will not be classified into any of the predictive segments.

&nbsp;

**Can a user who was classified into one of the predictive segments be reclassified into a different [!UICONTROL Predictive Audiences] segment?**

Yes. Since the algorithm is trained on a daily basis, it applies the changes for each of the personas in terms of trait scoring. If a user who is part of a [!UICONTROL Predictive Audiences] segment is active, the changes in their trait score can change the classification based on the past 30 days activity.

&nbsp;

**Can I see the traits by which audience classification is done?**

Yes, you can see all influential traits for all baselines in the model reporting page. See [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

&nbsp;

**Can I change the time to live (TTL) for predictive traits?**

Predictive trait TTL is set to 0 (lifetime) and cannot be changed. [!UICONTROL Predictive Audiences] can only unsegment users from predictive segments when they qualify for either the base segment or they get reclassified into a diferent predictive segment.

If needed, you can work around this functionality by creating a new segment that contains both a predictive trait and an activity trait with a specified TTL.

&nbsp;


**What happens to the model if I edit one of its baseline traits or segments?**

The model evaluates the traits or segments once a day. You should see the updated classification the next day after your update.

&nbsp;

**Can I select the data sources from which the model will learn?**

No, selection of data sources is not supported. The [!UICONTROL Predictive Audiences] algorithm learns from all your first party traits.
