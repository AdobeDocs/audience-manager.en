---
description: You can use several different types and sources of models in Audience Manager. Audience Lab offers an easy way to compare your customers' conversion rates, across your active models.
seo-description: You can use several different types and sources of models in Audience Manager. Audience Lab offers an easy way to compare your customers' conversion rates, across your active models.
seo-title: Compare Models in Audience Lab
solution: Audience Manager
title: Compare Models in Audience Lab
topic: DIL API
uuid: 8336555e-6631-4860-a70f-85ec88453f1a
index: y
internal: n
snippet: y
translate: y
---

# Compare Models in Audience Lab

In this use case, you are comparing different models. You can either use models created via an in-house data warehouse and import them in [!DNL  Audience Manager] as [ Onboarded Traits](../../../c_features/c_tb_overview/c_tb_main/c_trait_create/c_tb_rules_traits/c_tb_rules_traits.md#concept_CFCB78FDF44A42BCA69C948A2C8EC3D5) or you can use the [ Algorithmic Models](../../../c_features/c_models/c_models.md#concept_49FB2DBD4AD041A4ABAAEE9D83BB996E) feature in [!DNL  Audience Manager]. 

>1. Create two models, either in the [ Model Builder](../../../c_features/c_models/c_model_builder/c_model_builder.md#concept_25287B0C161F4BFCBCCFEB5CC6E613D0), or via an outside platform.
>1. Create [ algorithmic traits](../../../c_features/c_tb_overview/c_tb_main/c_trait_create/c_tb_algo_traits/t_algo_trait_build.md#task_E9A3F46A50C14450AE263775EECA0353) from the algorithmic model or import your own models as onboarded traits.
>1. Create mutually exclusive segments so users in both models don't overlap:
>    * Create a *Model 1 Segment* and a *Model 2 Segment*.
>    * Have the segment rule for *Model 1 Segment* be model 1 trait AND NOT model 2 trait, and vice-versa for *Model 2 Segment*.
>1. [ Create two segment test groups](../../../c_features/audience-lab/create-test-group.md#task_B62EF6D2992941FAAEA84BE2EA11A55E) in **[!UICONTROL  Audience Lab]**, one with *Model 1 Segment* as the baseline, the other with *Model 2 Segment* as the baseline.
>    * Keep the variables the same for both test groups: same destinations, creative, conversion traits.
>    * Make sure the test segments have similar numbers of users (e.g. 1.6 million and 1.8 million is alright, 1.6 million and 16 million is not).
>    * Reserve a control segment in each test segment test group. This way, you can set aside a small part of each segment and not target them explicitly in the test.
>1. Examine the results:
>    * The [ Audience Lab reporting view](https://marketing.adobe.com/resources/help/en_US/aam/audience-lab-reporting-view.html) will show the number of conversions each model is driving. For conversion based campaigns, the test segment that drives the most conversions will signify the model that is performing best.
>    * Because you have control segments, you can also evaluate how the model did against "standard targeting." You are not only just testing one model versus the other, but testing the question of "did this model do better than normal practices?"
