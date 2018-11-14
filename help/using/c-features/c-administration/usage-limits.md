---
description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Usage Limits
topic: DIL API
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
index: y
internal: n
snippet: y
---

# Usage Limits{#usage-limits}

Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.

Contents:

<ul class="simplelist"> 
 <li> <a href="../../c-features/c-administration/usage-limits.md#section_7181B0BBC194402BAC55E6846048D78F" format="dita" scope="local"> Item Limits </a> </li> 
 <li> <a href="../../c-features/c-administration/usage-limits.md#section_EBE3D23D14F54408911573211E2ED62D" format="dita" scope="local"> Monitor Usage </a> </li> 
 <li> <a href="../../c-features/c-administration/usage-limits.md#section_CAB5B9E4ED0D449A9DD97B04ECEF5838" format="dita" scope="local"> Increase Item Limits </a> </li> 
</ul>

## Item Limits {#section_7181B0BBC194402BAC55E6846048D78F}

The tables list the current limits by item type. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. If you do reach a limit, you must delete an older item before you can create a new one.

**Trait Limits**

<table id="table_8870FECEDF774EB2BAB225269656EC6A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait Type </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Total Traits</b> </p> </td> 
   <td colname="col2"> <p>100,000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Total Trait Qualifications</b> </p> </td> 
   <td colname="col2"> <p>100,000. For more information on trait qualification, see the <a href="../../c-features/traits/trait-qualification-reference.md#concept_C27644821296475A84A7522847D92C9D" format="dita" scope="local"> Trait Qualifications Reference</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Algorithmic</b> </p> </td> 
   <td colname="col2"> <p>50 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rule Based</b> </p> </td> 
   <td colname="col2"> <p>100,000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Onboarded</b> </p> </td> 
   <td colname="col2"> <p>100,000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Folder Traits</b> </p> </td> 
   <td colname="col2"> <p>2,000 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Segment Limits**

<table id="table_749EC62847C94855B624096F77850115"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segment Type </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Total Segments</b> </p> </td> 
   <td colname="col2"> <p>20,000 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Destination Limits**

<table id="table_A1DA42251B04408E900DA36F2F3EE9DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Destination Type </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Total Destinations</b> </p> </td> 
   <td colname="col2"> <p>1,000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Cookie</b> </p> </td> 
   <td colname="col2"> <p>1,000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>URL</b> </p> </td> 
   <td colname="col2"> <p>1,000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>S2S</b> </p> </td> 
   <td colname="col2"> <p>100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics</b> </p> </td> 
   <td colname="col2"> <p>10 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Algorithmic Model Limits**

<table id="table_2FE310C0642444EAB0347EFA4A0B6C68"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Total Algorithmic Models</b> </p> </td> 
   <td colname="col2"> <p>20 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Algorithmic Models maximum audience size</b> </p> </td> 
   <td colname="col2"> <p>25,000,000 </p> Note that this limit cannot be increased. You can decrease audience sizes by selecting fewer data sources for the model or by selecting a shorter look-back window. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Maximum number of excluded traits for a model</b> </p> </td> 
   <td colname="col2"> <p>500 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Folder Limits**

<table id="table_444C721A9F46474B9891BB8AC50FDD2A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Trait Folders</b> </p> </td> 
   <td colname="col2"> <p>2,000. </p> <p>Your folder structure can be maximum 5 levels deep. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Derived Signals Limits**

<table id="table_CFF910496D984C77AF57702238F30AD5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Derived Signals</b> </p> </td> 
   <td colname="col2"> <p>50,000. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Company User Accounts Limit**

<table id="table_50ECCACCFA2C4F009276A6AEE280AF6C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Maximum Limit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Maximum number of user accounts for a company</b> </p> </td> 
   <td colname="col2"> <p>1,000. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Monitor Usage {#section_EBE3D23D14F54408911573211E2ED62D}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. Access requires administrator permissions.

![](assets/usage_limits.jpg)

## Increase Item Limits {#section_CAB5B9E4ED0D449A9DD97B04ECEF5838}

The default limits listed here should provide enough capacity for your business needs. If your organization consistently reaches these limits, contact your account representative to discuss an increase. 
