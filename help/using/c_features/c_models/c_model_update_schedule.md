---
description: Creation and update schedules for new or existing algorithmic models and traits.
seo-description: Creation and update schedules for new or existing algorithmic models and traits.
seo-title: Update Schedule for Algorithmic Models and Traits
solution: Audience Manager
title: Update Schedule for Algorithmic Models and Traits
topic: DIL API
uuid: 825f58e9-5ef6-40ee-99cb-ddc96a094512
index: y
internal: n
snippet: y
translate: y
---

# Update Schedule for Algorithmic Models and Traits

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
     </ul> </p> <p>Models built or cloned after the creation deadline are processed the following day. </p> <p>If the first run of a model generates no data it will run a second time, the next day. If the second attempt also doesn't generate any data, there will be a third attempt, the next day. The model will stop running if the third attempt also doesn't generate any data. In this case, we will deactivate the model. See more in <a href="../../c_features/c_models/understanding-models.md#section_356A9E6C33FE4194A70DA6CA2AB511E9" format="dita" scope="local"> Troubleshooting Algorithmic Models</a>. </p> </td> 
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

