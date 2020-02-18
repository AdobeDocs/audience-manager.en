---
description: Smart Personas help you classify unknown audiences into distinct personas in real-time, using data science.
seo-description: Smart Personas help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Smart Personas FAQ
solution: Audience Manager
title: Audience Manager Smart Personas
---

# Smart Personas FAQ

Frequently asked questions about [!UICONTROL Smart Personas].

&nbsp;

**When should I use [!UICONTROL Smart Personas] as opposed to [!UICONTROL Look-alike modeling]?**

[!UICONTROL Smart Personas] and [!UICONTROL Look-alike modeling] serve different use cases. The main differences between the two algorithms are these:

1. The number of base segments is different for each algorithm. [!UICONTROL Smart Personas] requires at least two baselines, while [!UICONTROL Look-alike modeling] uses one baseline at most.
2. [!UICONTROL Smart Personas] performs real-time segment evaluation, while [!UICONTROL Look-alike modeling] does not.
3. [!UICONTROL Look-alike modeling] takes a small audience as input and expands it. [!UICONTROL Smart Personas] takes a large audience as input, and divides it into smaller distinct audiences, defined by your personas.

Based on your use case, you should decide which model will be more relevant to you.

You can think of building a [!UICONTROL Smart Personas] model with a number of baselines as being the equivalent of building the same number of look-alike models, only without the real-time evaluation, and with a very high likelihood to have visitors belonging to multiple different personas, instead of one distinct persona.

&nbsp;

**How many personas/models am I allowed to create?**

You can create up to 10 [!UICONTROL Smart Persona] models. For each model, you can define up to 50 baseline traits or segments.

&nbsp;

**How can I build new segments from a [!UICONTROL Smart Personas] segment?**

Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**, and click the **[!UICONTROL Smart Personas]** folder. Find the desired segment, duplicate it, and edit it according to your needs.

&nbsp;

**Why are some of my onboarded visitors not classified?**

Currently, audience classification only works for real time qualifications, except for authenticated users that were defined as part of [!UICONTROL Profile Merge Rules].

Full support for onboarded data will be added in a future update.

&nbsp;

**When can I see the first results produced by my model?**

[!UICONTROL Smart Personas] model results are available within 24 hours from model creation, if the model runs successfully.

In case the model does not produce results within 24 hours, please reach out to your Adobe representative.

&nbsp;

**Why is my model showing the Warning status?**

[!UICONTROL Smart Personas] models can fail to produce results due to a number of reasons:

1. None of the selected persona traits / segments have enough user profiles. We recommend choosing your traits or segments so that each persona has at least a few hundred user profiles.
1. None of the selected persona traits / segments have enough data in their user profiles (not enough traits to analyze).
1. The target audience trait / segment did not have any active or onboarded users within the past 30 days.
1. The target audience users that were active or onboarded within the past 30 days do not have enough data in their user profiles (not enough traits to analyze).

To produce relevant results, the [!UICONTROL Smart Personas] algorithm evaluates trait and segment realizations based on real-time user activity seen by the DCS. If you select new base traits and segments that do not yet have enough users, the algorithm may take a couple of days to classify your audience.

&nbsp;

**Why is my model showing the Error status?**

The model failed to run. In such cases, please reach out to your Adobe representative.

**How can I change the Profile Merge Rule for a Smart Personas segment?**

Duplicate the [!UICONTROL Smart Personas] segment and change the [!UICONTROL Profile Merge Rule] for the duplicated segment.

&nbsp;

**Could a user from the target audience who isn't part of any persona trait / segment not be classified?**

Yes, in case the user does not have any traits in his profile. In that case, the user will get a match score of 0 to all of the persona traits / segments, and therefore will not be classified into any of the [!UICONTROL Smart Personas] segments.

&nbsp;

**Can a user who was classified into one of the [!UICONTROL Smart Personas] segments be reclassified into a different [!UICONTROL Smart Personas] segment?**

Yes. Since the algorithm is trained on a daily basis, it applies the changes for each of the personas in terms of trait scoring. If a user who is part of a [!UICONTROL Smart Personas] segment is active, the changes in their trait score can change the classification based on the past 30 days activity.

&nbsp;

**Can I see the traits by which audience classification is done?**

Yes, you can see all influential traits for all baselines in the model reporting page. See [Influential Traits](../features/algorithmic-models/smart-personas-reporting.md#influential-traits).

&nbsp;

**What happens to the model if I edit one of its baseline traits or segments?**

The model evaluates the traits or segments once a day. You should see the updated classification the next day after your update.
