---
description: A review of algorithmic modeling in Audience Manager. Describes how modeling works, benefits, and workflow.
seo-description: A review of algorithmic modeling in Audience Manager. Describes how modeling works, benefits, and workflow.
seo-title: Understanding Algorithmic Models
solution: Audience Manager
title: Understanding Algorithmic Models
topic: DIL API
uuid: 93967a6e-b83e-4a90-83b3-2ae5ae8fd4f0
index: y
internal: n
snippet: y
translate: y
---

# Understanding Algorithmic Models

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../c_features/c_models/understanding-models.md#section_0243382004524AD1B1EEFB2D9F19E49E" format="dita" scope="local"> Find New Users with Algorithmic Modeling </a> </li> 
 <li> <a href="../../c_features/c_models/understanding-models.md#section_029CA57DD883400AA92018D07FB890B2" format="dita" scope="local"> Advantages </a> </li> 
 <li> <a href="../../c_features/c_models/understanding-models.md#section_9F5FFEF73A904D09A2910AE75C67B640" format="dita" scope="local"> Workflow </a> </li> 
</ul>



## Find New Users with Algorithmic Modeling {#section_0243382004524AD1B1EEFB2D9F19E49E}

Algorithmic modeling helps you discover new, unique audiences through automated data analysis. The process starts when you select a trait or segment, a time interval, and first and third-party data sources. Your choices provide the inputs for the algorithmic model. When the analytics process runs, it looks for eligible users based on shared characteristics from the selected population. Upon completion, this data is available in [ Trait Builder ](../../c_features/c_tb_overview/c_tb_main/c_tb_about.md#concept_13D6537EE5D0459F870C58822AD5400A) where you can use it to create traits based on [ accuracy and reach ](../../c_features/c_tb_overview/c_tb_reference/c_accuracy_reach.md#concept_60F696940483424CA4E8EEDD63F46358). Additionally, you can build segments that combine algorithmic traits with rules-based traits and add other qualification requirements with Boolean expressions and comparison operators. Algorithmic modeling gives you a dynamic way to extract value from all your available trait data. 

## Advantages {#section_029CA57DD883400AA92018D07FB890B2}

The major benefits of using [!DNL  Audience Manager] modeling include: 


* **Data accuracy:** The algorithm runs regularly, which helps keep results current and relevant.
* **Automation:** You don't have to manage a large set of static rules. The algorithm will find audiences for you.
* **Save time and reduce effort:** With our modeling process you don't have to guess at what traits/segments may work or spend time resources on campaigns to discover new audiences. The model can do this for you.
* **Reliability:** Modeling works with server-side discovery and qualification processes that evaluate your own data and selected third-party data that you have access to. This means you don't have to see the visitors on your site to qualify them for a trait.


## Workflow {#section_9F5FFEF73A904D09A2910AE75C67B640}

You manage models in **[!UICONTROL  Audience Data > Models]**. At a high level, the workflow process involves the following: 


* Select the baseline data you want the algorithm to evaluate. This includes a trait or segment, time range, and data sources (your own data and third-party data you already have access to through [!DNL  Audience Manager]).
* Save your model. Once saved, algorithmic evaluation process runs automatically. Note, however, it can take up to 7 days for this process to complete. [!DNL  Audience Manager] sends you an email when the algorithm has finished and results are available for trait creation.
* Build algorithmic traits in [!UICONTROL  Trait Builder].
* Combine traits into segments in [!UICONTROL  Segment Builder].
* Create and send segment data to a destination.


## Troubleshooting {#section_356A9E6C33FE4194A70DA6CA2AB511E9}

We deactivate any algorithmic model that fails to generate data for three consecutive runs. Note that you cannot set the status of the model back to active afterwards. To ensure your models generate data, we recommend that you build models from data sources with sufficient traits to accumulate data from. 
>[!MORE_LIKE_THIS]
>
>* [ Destinations ](c_destinations.md#concept_5BDA346C376C4B719EA394108AB2735A)
>* [ Traits ](c_tb_overview.md#concept_422CE72B2125457B8C2954BF06102332)
>* [ Segments ](c_segments.md#concept_2044B3AC34AC46669EE7D9292380BE0C)
