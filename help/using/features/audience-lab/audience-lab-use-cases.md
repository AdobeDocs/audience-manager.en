---
description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Audience Lab Use Cases
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
---

# [!UICONTROL Audience Lab] Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.

## Compare Models in [!UICONTROL Audience Lab] {#task_DB23E5242DAA4183949E90715F7DAA32}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] offers an easy way to compare your customers' conversion rates, across your active models.

<!-- 
audience-lab-compare-models.xml
-->

In this use case, you are comparing different models. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md#concept_49FB2DBD4AD041A4ABAAEE9D83BB996E) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md#concept_25287B0C161F4BFCBCCFEB5CC6E613D0), or via an outside platform.
2. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
3. Create mutually exclusive segments so users in both models don't overlap:

    * Create a *Model 1 Segment* and a *Model 2 Segment*.
    * Have the segment rule for *Model 1 Segment* be model 1 trait AND NOT model 2 trait, and vice-versa for *Model 2 Segment*.

4. [Create two segment test groups](../../features/audience-lab/audience-lab-manage-test-groups.md#task_B62EF6D2992941FAAEA84BE2EA11A55E) in [!UICONTROL Audience Lab], one with *Model 1 Segment* as the baseline, the other with *Model 2 Segment* as the baseline.

    * Keep the variables the same for both test groups: same destinations, creative, conversion traits.
    * Make sure the test segments have similar numbers of users (e.g. 1.6 million and 1.8 million is alright, 1.6 million and 16 million is not).
    * Reserve a control segment in each test segment test group. This way, you can set aside a small part of each segment and not target them explicitly in the test.

5. Examine the results:

    * The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md#concept_C8A089E2B1C54D268C4F6475C4D5C9D6) will show the number of conversions each model is driving. For conversion based campaigns, the test segment that drives the most conversions will signify the model that is performing best. 
    * Because you have control segments, you can also evaluate how the model did against "standard targeting." You are not only just testing one model versus the other, but testing the question of "did this model do better than normal practices?"

## Testing Creatives Across Destinations {#task_7AF1E1FE31034EF5AB77226D9D75E4E6}

<!-- 
audience-lab-creatives-across-destinations.xml
-->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. This use case also allows you to measure the conversions of the creative against naturally occurring conversions.

1. [Create a Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#task_B62EF6D2992941FAAEA84BE2EA11A55E), selecting the segment you want to test the creative against as the baseline segment.
1. Split the baseline segment into test segments and control segments.
1. Map the test segments to the different destinations you wish to test.
1. The control segment can be withheld and not mapped to any destination. The control segment should not be targeted by the test creative to set a results baseline for naturally occurring conversions.
1. Specify a start date and an end date for the test.
1. Set up the segment and the creative in the destinations.
1. The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md#concept_C8A089E2B1C54D268C4F6475C4D5C9D6) will show the number of conversions the creative is driving across the destinations.
1. Because you created a control segment, you can also evaluate how the creative did against naturally occurring conversions. You are testing the question: "Did this creative generate a higher conversion rate than normal practices?"
