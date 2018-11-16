---
description: Build and manage the traits or segments used in algorithmic modeling, also referred to as look-alike modeling. Model features are located in Audience Data > Models.
keywords: RBAC;rbac
seo-description: Build and manage the traits or segments used in algorithmic modeling, also referred to as look-alike modeling. Model features are located in Audience Data > Models.
seo-title: About Algorithmic Models
solution: Audience Manager
title: About Algorithmic Models
topic: DIL API
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
index: y
internal: n
snippet: y
---

# About Algorithmic Models{#about-algorithmic-models}

Build and manage the traits or segments used in algorithmic modeling, also referred to as look-alike modeling. Model features are located in Audience Data > Models.

## About Algorithmic Models {#concept_49FB2DBD4AD041A4ABAAEE9D83BB996E}

Build and manage the traits or segments used in algorithmic modeling, also referred to as look-alike modeling. Model features are located in Audience Data > Models.

<!-- 

c_models.xml

 -->

## Understanding Algorithmic Models {#concept_441E566718B845929880B0823A9ECA9F}

A review of algorithmic modeling in [!DNL Audience Manager]. Describes how modeling works, benefits, and workflow.

<!-- 

understanding-models.xml

 -->

## Find New Users with Algorithmic Modeling {#section_0243382004524AD1B1EEFB2D9F19E49E}

Algorithmic modeling helps you discover new, unique audiences through automated data analysis. The process starts when you select a trait or segment, a time interval, and first and third-party data sources. Your choices provide the inputs for the algorithmic model. When the analytics process runs, it looks for eligible users based on shared characteristics from the selected population. Upon completion, this data is available in [Trait Builder](../../c-features/traits/about-trait-builder.md#concept_13D6537EE5D0459F870C58822AD5400A) where you can use it to create traits based on [accuracy and reach](../../c-features/traits/trait-accuracy-reach.md#concept_60F696940483424CA4E8EEDD63F46358). Additionally, you can build segments that combine algorithmic traits with rules-based traits and add other qualification requirements with Boolean expressions and comparison operators. Algorithmic modeling gives you a dynamic way to extract value from all your available trait data.

## Advantages {#section_029CA57DD883400AA92018D07FB890B2}

The major benefits of using [!DNL Audience Manager] modeling include:

* **Data accuracy:** The algorithm runs regularly, which helps keep results current and relevant. 
* **Automation:** You don't have to manage a large set of static rules. The algorithm will find audiences for you. 
* **Save time and reduce effort:** With our modeling process you don't have to guess at what traits/segments may work or spend time resources on campaigns to discover new audiences. The model can do this for you. 
* **Reliability:** Modeling works with server-side discovery and qualification processes that evaluate your own data and selected third-party data that you have access to. This means you don't have to see the visitors on your site to qualify them for a trait.

## Workflow {#section_9F5FFEF73A904D09A2910AE75C67B640}

You manage models in **[!UICONTROL Audience Data > Models]**. At a high level, the workflow process involves the following:

* Select the baseline data you want the algorithm to evaluate. This includes a trait or segment, time range, and data sources (your own data and third-party data you already have access to through [!DNL Audience Manager]). In the model creation workflow, you can exclude the traits that you don't want to interfere with your model. 
* Save your model. Once saved, algorithmic evaluation process runs automatically. Note, however, it can take up to 7 days for this process to complete. [!DNL Audience Manager] sends you an email when the algorithm has finished and results are available for trait creation. 
* Build algorithmic traits in [!UICONTROL Trait Builder]. 
* Combine traits into segments in [!UICONTROL Segment Builder]. 
* Create and send segment data to a destination.

## Troubleshooting {#section_356A9E6C33FE4194A70DA6CA2AB511E9}

We deactivate any algorithmic model that fails to generate data for three consecutive runs. Note that you cannot set the status of the model back to active afterwards. To ensure your models generate data, we recommend that you build models from data sources with sufficient traits to accumulate data from. 

>[!MORE_LIKE_THIS]
>
>* [Destinations](../../c-features/destinations/destinations.md#concept_5BDA346C376C4B719EA394108AB2735A)
>* [Traits](../../c-features/traits/traits.md#concept_422CE72B2125457B8C2954BF06102332)
>* [Segments](../../c-features/c-segments/c-segments.md#concept_2044B3AC34AC46669EE7D9292380BE0C)

## Understanding <wintitle> TraitWeight </wintitle> {#concept_1E21CF71FBD04C3EA59554909828DAD5}

[!UICONTROL TraitWeight] is a proprietary algorithm designed to discover new traits automatically. It compares trait data from your current traits and segments against all other first and third-party data that you have access to through [!DNL Audience Manager]. Refer to this section for a description of the [!UICONTROL TraitWeight] algorithmic discovery process.

<!-- 

traitweight.xml

 -->

![](assets/algo_model.png)

The following steps describe the [!UICONTROL TraitWeight] evaluation process.

**Step 1: Build a Baseline for Trait Comparison**

To build a baseline, TraitWeight measures all the traits associated with an audience for a 30, 60, or 90-day interval. Next, it ranks traits according to their frequency and their correlation. The frequency count measures commonality. Correlation measures the likelihood of a trait being present only in the baseline audience. Traits that appear often are said to exhibit high commonality, an important characteristic used to set a weighted score when combined with traits discovered in your selected data sources.

**Step 2: Find the Same Traits in the Data Source**

After it builds a baseline for comparison, the algorithm looks for identical traits in your selected data sources. In this step, TraitWeight performs a frequency count of all discovered traits and compares them to the baseline. However, unlike the baseline, uncommon traits are ranked higher than those that appear more often. Rare traits are said to exhibit a high degree of specificity. TraitWeight assesses combinations of common baseline traits and uncommon (highly specific) data source traits as more influential or desirable than traits common to both data sets. In fact, our model recognizes these large, common traits and does not assign excess priority to data sets with high correlations. Rare traits get higher priority because they are more likely to represent new, unique users than traits with high commonality across the board.

**Step 3: Assign Weight**

In this step, TraitWeight ranks newly discovered traits in order of influence or desirability. The weight scale is a percentage that runs from 0% to 100%. Traits ranked closer to 100% means they're more like the audience in your baseline population. Also, heavily weighted traits are valuable because they represent new, unique users who may behave similarly to your established, baseline audience. Remember, TraitWeight considers traits with high commonality in the baseline and high specificity in the compared data sources to be more valuable than traits common in each data set.

**Step 4: Scoring Users**

Each user in the selected data sources is given a user score which is equal to the sum of all the weights of the influential traits on that user's profile. The user scores are then normalized between 0 and 100%.

**Step 5: Display and Work with Results**

Audience Manager displays your weighted model results in [!UICONTROL Trait Builder]. When you want to build an algorithmic trait, [!UICONTROL Trait Builder] lets you create traits based on the weighted score generated by the algorithm during a data run. You can choose a higher accuracy to only qualify users who have very high user scores and therefore are very similar to the baseline audience, rather than the rest of the audience. If you want to reach a larger audience (reach), you can lower the accuracy.

**Step 6: Re-evaluate the Significance of a Trait Across Processing Cycles**

Periodically, TraitWeight re-evaluates the importance of a trait based on the size and change in the population of that trait. This happens as the number of users qualified for that trait increases or decreases over time. This behavior is most clearly seen in traits that become very large. For example, suppose the algorithm uses trait A for modeling. As the population of trait A increases, TraitWeight re-evaluates the importance of that trait and may assign a lower score or ignore it. In this case, trait A is too common or large to say anything significant about its population. After TraitWeight reduces the value of Trait A (or ignores it in the model), the population of the algorithmic trait decreases. The list of influential traits reflects the evolution of the baseline population. Use the list of the influential traits to understand why these changes are occurring. 

>[!MORE_LIKE_THIS]
>
>* [Model Builder](../../c-features/algorithmic-models/create-model.md#concept_25287B0C161F4BFCBCCFEB5CC6E613D0)
>* [Accuracy and Reach](../../c-features/traits/trait-accuracy-reach.md#concept_60F696940483424CA4E8EEDD63F46358)

## Update Schedule for Algorithmic Models and Traits {#concept_55C98FC0E4C749F5A2FE8B2BA2EA9D6A}

Creation and update schedules for new or existing algorithmic models and traits.

<!-- 

c_model_update_schedule.xml

 -->

**Algorithmic Model Creation and Update Schedule**

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Activity Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Create or Clone a Model</b> </td> 
   <td colname="col2"> <p>For new or cloned algorithmic models, the creation process runs once per day at: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (November - March) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (March - November) </li> 
     </ul> </p> <p>Models built or cloned after the creation deadline are processed the following day. </p> <p>If the first run of a model generates no data it will run a second time, the next day. If the second attempt also doesn't generate any data, there will be a third attempt, the next day. The model will stop running if the third attempt also doesn't generate any data. In this case, we will deactivate the model. See more in <a href="../../c-features/algorithmic-models/understanding-models.md#section_356A9E6C33FE4194A70DA6CA2AB511E9"> Troubleshooting Algorithmic Models</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Update a Model</b> </td> 
   <td colname="col2"> <p>Under ideal conditions, existing models run on weekdays, at least once every 7 days. For example, if you create a model (by the deadline) on Monday, it updates the following Monday at the latest. </p> <p>A model will rerun if it meets any of the following conditions: </p> <p> 
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Its last run was not successful. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">It has run successfully before AND it has not run at all in the past 7 days AND the model has at least one active trait attached to it. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Algorithmic Trait Creation and Update Schedule**

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Activity Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Create a Trait</b> </td> 
   <td colname="col2"> <p>The trait creation process runs every day, Monday through Friday. Generally, new algorithmic traits appear in the UI within 48 hours. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Update a Trait</b> </td> 
   <td colname="col2"> <p>Existing traits are updated at least once every 7 days and follow the schedule for model updates. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Models List View {#concept_E24227A375164638929A42FEA533B1E7}

The list view is a central workspace that helps you to create, review, and manage models.

<!-- 

c_models_list_view.xml

 -->

The Models list page contains features and tools that help you:

* Create new models. 
* Manage existing models (edit, pause, delete, or clone). 
* Search for models by name. 
* Create algorithmic traits using any given model.

## Models Summary View {#concept_46E124E03A8A4A7C88FA9344E7D57974}

The summary page displays model details such as name, reach/accuracy, processing history, and traits created from the model. The page also includes settings that let you create and managing models. Click a model name from the summary list to see its details.

<!-- 

c_models_summary.xml

 -->

The model summary page includes the following sections.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Section </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Basic Information</span> </p> </td> 
   <td colname="col2"> <p>Includes basic information about the model such as its name and when it last ran. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Model Reach and Accuracy</span> </p> </td> 
   <td colname="col2"> <p>Shows <a href="../../c-features/traits/trait-accuracy-reach.md#concept_60F696940483424CA4E8EEDD63F46358"> accuracy and reach</a> data for the last model run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Model Processing History</span> </p> </td> 
   <td colname="col2"> <p>Displays the processing date and time for the last 10 runs and whether data was generated on those runs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influential Traits</span> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Influential Traits</span> table: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lists the top 50 influential traits that are best represented in the model's baseline population. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ranks each trait in order of its <span class="wintitle"> Relative Weight</span> rank. The <span class="wintitle"> Relative Weight</span> sorts newly discovered traits in order of influence or desirability. The weight scale is a percentage that runs from 0% to 100%. Traits ranked closer to 100% means they're more like the audience in your baseline population. See <a href="../../c-features/algorithmic-models/understanding-models.md#concept_1E21CF71FBD04C3EA59554909828DAD5"> Understanding TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Shows the 30-Day uniques and the total trait population for each trait. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Traits Using Model</span> </p> </td> 
   <td colname="col2"> <p>Shows a list of the algorithmic traits based on the selected model. Click a trait name or trait ID for more information on the trait. Select <span class="uicontrol"> Create New Trait with Model</span> to go to the algorithmic trait creation process. </p> <p>The section label changes based on the name of your model. For example, say you create a model and name it Model A. When you load the summary page, the name of this section gets changed to <span class="wintitle"> Traits Using Model A</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

