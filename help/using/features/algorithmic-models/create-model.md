---
description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
keywords: algo how works
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Create an Algorithmic Model
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
---

# Create a Look-Alike Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create a [!UICONTROL Look-Alike Model].

## Model Builder Section

[!UICONTROL Model Builder] consists of the [!UICONTROL Basic Information] and [!UICONTROL Configuration] sections. To create a model, complete the required fields in these two sections. Save your model to start the algorithm. [!DNL Audience Manager] sends you an automated notification after the first data run completes. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* The modeling process runs only once if you create a model and do not build any traits with it.
>* Build models from data sources that contain a meaningful amount of information. Models with insufficient data will run, but they will not return results.
>* *Do not* create models with other algorithmic traits or segments.
>* The automated email notification is sent one time only (after the first data run).

## Build the Model

Follow the steps below to build a [!UICONTROL Look-Alike Model]:

1. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** and click **[!UICONTROL Add New]** in the [!UICONTROL Look-Alike Modeling] section.
    ![look-alike-add](assets/look-alike-add.png)
2. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
    * Name the model.
    * *(Optional)* Provide a brief description about the model.
    * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. Inactive models will not run and will not produce any data.
    ![look-alike-basic](assets/look-alike-basic.png)
3. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
    * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. Select an onboarded trait, a rule-based trait, or a segment as baseline. Otherwise, your models will not run.
    * Choose a 30, 60, or 90 day look-back period. This sets a time range for the model.
    * The [!UICONTROL TraitWeight] algorithm is selected by default.
    * Select a data source from the [!UICONTROL Available Data] list.
    * Click **[!UICONTROL Save]** when done.
    ![look-alike-configuration](assets/look-alike-configuration.png)

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. The description field is optional.

|  Field  | Description  |
|---|---|
|  **[!UICONTROL Name]** | Give your model a short, logical name that describes its function or purpose. Avoid abbreviations, special characters, and accent marks.  |
|  **[!UICONTROL Description]** | A field for additional descriptive information about the model.  |
|  **[!UICONTROL Status]** | Activates or deactivates the model (active by default). |

## Configuration {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. In this section, select a baseline trait or segment, a look-back period, and data from your first and third-party data sources.

<!-- r_model_configuration.xml -->

### Prerequisites

Complete the required fields in the [!UICONTROL Basic Information] section first.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Select a Baseline Trait or Segment (1)</b> </p> </td> 
   <td colname="col2"> <p>Click the trait or segment button to see a list of all your traits or segments. Your selected segment or trait becomes the baseline that the system algorithms use for modeling. </p> <p> <p><b>Note</b>:  Select an onboarded trait, a rule-based trait, or a segment as baseline. Otherwise, your models will not run. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Select Look Back Period (2)</b> </p> </td> 
   <td colname="col2"> <p>Sets a time range for the model. Based on your selection, the algorithm includes and evaluates data from the previous 30, 60, or 90 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Select Algorithm (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> may add other algorithmic functions in subsequent releases. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Select Model Data from Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Lets you select the first and third-party data sources you want to use in the model. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>You can exclude traits from the data sources you selected for modeling. Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

Watch the video below to learn how to create a first party look-alike model, so that you can find more of your own visitors who look like your converters.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Understanding TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
