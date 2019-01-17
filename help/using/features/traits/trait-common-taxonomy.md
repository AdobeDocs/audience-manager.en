---
description: This article provides general overview about classifying traits with a common taxonomy.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Classifying Traits with a Common Taxonomy
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
---

# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

This article provides general overview about classifying traits with a common taxonomy.

## The Audience Manager Taxonomy

<!-- 

c_common_taxonomy_about.xml

 -->

The [!DNL Audience Manager] taxonomy is an optional feature that classifies traits using uniform, logical, and commonly understood naming conventions. It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. Ultimately, the common taxonomy is designed to bring our product into greater alignment with industry standards regarding consumer privacy and opt-out processes.

## Advantages of Trait Classification

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. What is also required, however, is a robust and scalable means to communicate information about segments to your customers and partners. Furthermore, this communication requires that segment information is shared in an easy-to-understand and universally understood language while protecting your proprietary trait and segment names. The [!DNL Audience Manager] common taxonomy provides this language and capability.

## The Taxonomy Uses Industry Standard Classification Categories

The common taxonomy is based on the classifications created by the Interactive Advertising Bureau (IAB). Refer to the IAB's [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## Taxonomic Organization

The [!DNL Audience Manager] taxonomy organizes data into nested categories called tiers. Each category can contain up to 3 separate tiers for data classification. At the highest level, a Tier 1 category groups data into its most general form (e.g., geography). Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --> United States --> New York*). However, not every category has 3 tiers, some use just 2.

## Classify Traits in Data Categories

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## Working With the Taxonomy: Additional Considerations

If you decide to classify traits according to our common taxonomy, it's important to remember:

* Classification is *optional*. 
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as "unknown" or "uncategorized" etc.). 
* Traits can belong to *one* taxonomic category only (multiple and cross-category classifications are not allowed).