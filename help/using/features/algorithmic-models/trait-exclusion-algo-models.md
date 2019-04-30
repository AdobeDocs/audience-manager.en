---
description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Algorithmic Models  Trait Exclusion
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
---

# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Use Cases {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] enables you to exclude certain catch-all traits, such as site visitor traits, so you don't bias the model, leading to flat results.
* You can remove traits that you don't know about or you don't trust from a data source, to better understand the influential traits.
* You can exclude certain traits, such as demographic traits, to help with any compliance obligations you may have.

>[!IMPORTANT]
>
>An important note on the third use case. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. You cannot exclude traits from modeling after creating the model. See [Important Aspects & Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Please exercise caution when using this feature and work with the data provider to ensure you are informed of any changes to the feed structure.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. The [!UICONTROL Exclusions] selection is greyed out until you select one or more data sources for modeling.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. In the **[!UICONTROL Select Traits to Exclude]** window, you can see all traits associated with the data sources you selected previously. Select the traits you want to exclude.
4. You can filter the traits by trait type, or you can browse the trait folders. Note that trait folders only display the traits associated with your selected data sources.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>You can exclude entire folders by excluding the folder trait instead of excluding the traits in the folder, one by one. For example, in a folder with 20 traits, you would only need to exclude the folder trait instead of excluding all the traits one by one.

If you prefer video tutorials, watch our video demonstration for Trait Exclusion: 

[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

## Important Aspects & Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Excluded Traits in Models Summary View </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Role-Based Access Controls (RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modify excluded traits after saving model </p> </td>
   <td colname="col2"> <p>You cannot modify the excluded traits after you have created and saved a model. If you want to tweak the results, you can clone the model and change the excluded traits. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximum number of traits you can exclude </p> </td>
   <td colname="col2"> <p>The maximum number of traits you can exclude from a model is 500. Use folder traits to maximize your exclusions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclude baseline trait </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## Related Links

* [About Algorithmic Traits](/help/using/features/algorithmic-models/understanding-models.md)
* [Trait Exclusion - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)