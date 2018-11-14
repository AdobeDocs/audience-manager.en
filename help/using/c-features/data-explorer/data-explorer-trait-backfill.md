---
description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: Backfill Trait Realizations
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
index: y
internal: n
snippet: y
---

# Backfill Trait Realizations{#backfill-trait-realizations}

Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.

<a id="section_20806EB397654461B1C5D78F411B7B04"></a>

When you create traits from unused signals, you can choose to backfill the trait realizations over a specific period of time. [!DNL Audience Manager] captures the historical data about audiences that qualify for the new trait and stores them on the corresponding profile. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the ** [Trait Builder](../../c-features/traits/about-trait-builder.md#concept_13D6537EE5D0459F870C58822AD5400A)**.

>[!NOTE]
>
>To enable trait backfilling, upgrade to [!UICONTROL Data Explorer Premium]. Contact your [!DNL Adobe] consultant for details.

Here's how to backfill trait realizations:

* Run a [Signals Search](../../c-features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md#concept_B0C0DC44C3EC4CF8926847F9062F0EC0) or use the [Signals Dashboard](../../c-features/data-explorer/data-explorer-signals-dashboard.md#concept_5E4B0FB02D8F4F3DAA5B6F8CF9A4E4C2) to identify the signals to use in the new trait. 

* Create a new trait based on the desired signals. 
* Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. Predefined backfill intervals include 1, 7, 14, and 30 days. You can also choose a custom date range of up to 30 days.

  ![](assets/signals-trait-backfill.png)

* (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.

  ![](assets/estimate-trait-realizations.png)

  >[!IMPORTANT]
  >
  >Trait backfilling and estimation are not available for traits with expressions that use the following operators:   >
  >    
  >    
  >    * `!=` 
  >    * `matchesregex` 
  >    * `matcheswords` 
  >    
  >

* Create the trait.

Once you finish creating the trait, you'll see its backfilled realizations included in the realization statistics.

## Trait Backfilling Latency {#section_834679B1592F436391DB8B1409551563}

Newly created traits start capturing audiences two to three hours after creation. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#section_3EE78E74377744149CEAD13B27A34FCD}

Data Explorer allows you to backfill up to 50 traits per month, with the backfill counter being reset on the 1 day of each month. 

>[!NOTE]
>
>Trait backfilling quota does not carry over from previous months. E.g., if you backfill 30 traits this month, the trait backfill quota for the next month is reset to 50, not 70.

## Impact on Reporting {#section_7B9BADB64AFE49C488DE9ED2B54EE05E}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date. 