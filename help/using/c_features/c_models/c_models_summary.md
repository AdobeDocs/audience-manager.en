---
description: The summary page displays model details such as name, reach/accuracy, processing history, and traits created from the model. The page also includes settings that let you create and managing models. Click a model name from the summary list to see its details.
keywords: RBAC;rbac
seo-description: The summary page displays model details such as name, reach/accuracy, processing history, and traits created from the model. The page also includes settings that let you create and managing models. Click a model name from the summary list to see its details.
seo-title: Models Summary View
solution: Audience Manager
title: Models Summary View
topic: DIL API
uuid: d47ef156-0c42-4276-bc11-6875b5f28986
index: y
internal: n
snippet: y
translate: y
---

# Models Summary View

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
   <td colname="col2"> <p>Shows <a href="../../c_features/c_tb_overview/c_tb_reference/c_accuracy_reach.md#concept_60F696940483424CA4E8EEDD63F46358" format="dita" scope="local"> accuracy and reach</a> data for the last model run. </p> </td> 
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
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ranks each trait in order of its <span class="wintitle"> Relative Weight</span> rank. The <span class="wintitle"> Relative Weight</span> sorts newly discovered traits in order of influence or desirability. The weight scale is a percentage that runs from 0% to 100%. Traits ranked closer to 100% means they're more like the audience in your baseline population. See <a href="../../c_features/c_models/traitweight.md#concept_1E21CF71FBD04C3EA59554909828DAD5" format="dita" scope="local"> Understanding TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Shows the 30-Day uniques and the total trait population for each trait. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Traits Using Model</span> </p> </td> 
   <td colname="col2"> <p>Shows a list of the algorithmic traits based on the selected model. Click a trait name or trait ID for more information on the trait. Select <span class="uicontrol"> Create New Trait with Model</span> to go to the algorithmic trait creation process. </p> <p>The section label changes based on the name of your model. For example, say you create a model and name it Model A. When you load the summary page, the name of this section gets changed to <span class="wintitle"> Traits Using Model A</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

