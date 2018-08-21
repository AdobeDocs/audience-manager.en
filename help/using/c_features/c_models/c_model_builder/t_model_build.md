---
description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
keywords: RBAC;rbac
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Build a Model
solution: Audience Manager
title: Build a Model
topic: DIL API
uuid: 3fafa77a-2d1f-4aab-9464-0e55d3a04b08
index: y
internal: n
snippet: y
translate: y
---

# Build a Model

**Model Builder Section** 

Model Builder consists of the [!UICONTROL  Basic Information] and [!UICONTROL  Configuration] sections. To create a model, complete the required fields in these two sections. Save your model to start the algorithm. Audience Manager sends you an automated notification after the first data run completes. After you receive the email, you can go to [ Trait Builder](../../../c_features/c_tb_overview/c_tb_main/c_tb_about.md#concept_13D6537EE5D0459F870C58822AD5400A) and create algorithmic traits. 
>[!NOTE]
>
>
>* The modeling process runs only once if you create a model and do not build any traits with it.
>* Build models from data sources that contain a meaningful amount of information. Models with insufficient data will run, but they will not return results.
>* *Do not* create models with other algorithmic traits or segments.
>* The automated email notification is sent one time only (after the first data run).




**Build a Model** 

To build a model, go to the [!UICONTROL  Models] section and click **[!UICONTROL  Add New]** and follow the steps below: 

>1. In the [ Basic Information](../../../c_features/c_models/c_model_builder/r_model_basic.md#reference_032EEDAE946B491C92BCE61E62AB7369) section

>    
>    * Name the model.
>    * *(Optional)* Provide a brief description about the model.
>    * Set the status for the model to **[!UICONTROL  Active]** or **[!UICONTROL  Inactive]**. Inactive models will not run and will not produce any data.
>1. In the [ Configuration](../../../c_features/c_models/c_model_builder/r_model_configuration.md#reference_E58E9C688E3144BEB2F75BCCDDF80B59) section:

>    
>    * Click **[!UICONTROL  Browse All Traits]** or **[!UICONTROL  Browse All Segments]** to select a trait or segment you want to model against. Select an onboarded trait, a rule-based trait, or a segment as baseline. Otherwise, your models will not run.
>    * Choose a 30, 60, or 90-day look-back period. This sets a time range for the model.
>    * The Trait Weight algorithm is selected by default.
>    * Select a data source from the [!UICONTROL  Available Data] list.
>    * Click **[!UICONTROL  Save]** when done.
