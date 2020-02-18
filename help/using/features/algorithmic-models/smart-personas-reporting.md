---
description: Smart Personas help you classify unknown audiences into personas in real-time, using advanced data science techniques.
seo-description: Smart Personas help you classify unknown audiences into personas in real-time, using advanced data science techniques.
seo-title: Smart Personas Reporting
solution: Audience Manager
title: Audience Manager Smart Personas
---

# Smart Personas Reporting

After you save a [!UICONTROL Smart Personas] model, Audience Manager immediately starts training it. Within a couple of hours, the computed model will start analyzing audiences on the [Data Collection Servers](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Reporting will be available the following day.

To see the results of your [!UICONTROL Smart Personas] classification, go to **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, and click your model in the list.

Use the filtering options on the left hand side to search for the model name or filter the results based on model type.

![smart-personas-filter](assets/smart-personas-filter-models.png)

The models table shows you the following information:

* **[!UICONTROL ID]**: the model ID uniquely identifies each model in your Audience Manager account;
* **[!UICONTROL Name]**: the name that you provided in the model creation step;
* **[!UICONTROL Description]**: the description that you provided in the model creation step;
* **[!UICONTROL Model Type]**: the type of each model ([!UICONTROL Look-Alike Modeling] or [!UICONTROL Smart Personas]).
* **[!UICONTROL Status]**: the status of each model:
  * **[!UICONTROL Pending]**: the model is initializing and will start producing results shortly;
  * **[!UICONTROL Active]**: the model is running successfully and producing results;
  <!-- * **[!UICONTROL Warning]**: the model produces results, but due to insufficient data (i.e. low baselines population, user profiles are not rich). -->
  * **[!UICONTROL Error]**: the model failed to run. You should contact your Adobe representative.

## Model Overview Report{#model-report}

Once you choose a model, its reporting page will load. At the top of the page you can see the top 5 largest [!UICONTROL Smart Personas] segments, based on 1 day real-time realization, that the model has classified your target audience by. The **[!UICONTROL Other]** category includes the rest of the personas, which were not included in the top 5 largest [!UICONTROL Smart Personas] segments.

Audience Manager displays both a color coded donut chart and a timeline graph for your [!UICONTROL Smart Personas].

Clicking the personas tabs at the top of the page adds or removes them from the chart and graph.

The donut chart shows you a persona-based breakdown of your target audience, while the graph shows you the 1-day real time population trend of your [!UICONTROL Smart Personas] segments over the past 6 days.

If the model status is [!UICONTROL Pending], [!UICONTROL Warning], or [!UICONTROL Error], the model status is displayed instead of the graphs.

![smart-persona-report](assets/smart-personas-report.png)

The report table shows you the following information for each [!UICONTROL Smart Personas] segment.

1. **[!UICONTROL SEGMENT ID]**: the segment ID of the auto-created segment associated to each persona;
1. **[!UICONTROL NAME]**: the persona name;
1. **[!UICONTROL STATUS]**: the status of the [!UICONTROL Smart Personas] segment:
   * **[!UICONTROL Succeeded]**: users are being classified into this segment;
   * **[!UICONTROL Pending]**: the segment is still being initialized;
   * **[!UICONTROL Insufficient Training Data]**: users are not being classified into this segment due to insufficient data. The total baseline population is too low and does not provide enough data to learn from.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: The number of segment realizations for each persona, over the past 24 hours.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: The percentage of segment realizations for each persona, over the past 24 hours, out of the total model population.

## Influential Traits{#influential-traits}

[!UICONTROL Influential Traits]

1. **[!UICONTROL TRAIT ID]**: the segment ID of each influential trait for the selected persona;
1. **[!UICONTROL NAME]**: the name of each influential trait for the selected persona;
1. **[!UICONTROL DESCRIPTION]**: the description of each influential trait for the selected persona;
1. **[!UICONTROL WEIGHT]**: the weight of each influential trait for the selected persona, calculated based on the [TraitWeight](understanding-models.md#understanding-traitweight) algorithm.
1. **[!UICONTROL UNIQUE TRAIT REALIZATIONS]**: the number of unique trait realizations for each influential trait for the selected persona;
1. **[!UICONTROL TOTAL TRAIT POPULATION]**: the total trait population of each influential trait for the selected persona.
