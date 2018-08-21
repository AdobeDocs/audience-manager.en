---
description: The settings in the different sections of the Data Source management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the Onboarding Status Report.
seo-description: The settings in the different sections of the Data Source management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the Onboarding Status Report.
seo-title: Data Source Settings and Menu Options
solution: Audience Manager
title: Data Source Settings and Menu Options
uuid: 4c021300-ed3e-481f-a95c-079578ae238b
index: y
internal: n
snippet: y
translate: y
---

# Data Source Settings and Menu Options


>Contents: 

>
<ul class="simplelist"> 
 <li> <a href="../../c_features/c_datasources/datasource-settings-definitions.md#section_43423119AD0E42A8B4C01747747E49A2" format="dita" scope="local"> Data Source Details </a> </li> 
 <li> <a href="../../c_features/c_datasources/datasource-settings-definitions.md#section_38F7E2A550A44A079BA8C26148B25349" format="dita" scope="local"> Data Export Controls </a> </li> 
 <li> <a href="../../c_features/c_datasources/datasource-settings-definitions.md#section_423704D358D049738DBA4216FEFFF798" format="dita" scope="local"> Data Source Settings </a> </li> 
</ul>



## Data Source Details {#section_43423119AD0E42A8B4C01747747E49A2}

In addition to text fields, the [!UICONTROL  Data Source Details] section contains the controls and options listed below. 



<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Menu Options </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> ID Type</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <span class="uicontrol"> Cookie</span>: The cookie ID that identifies a device. You would select this when your data source is a web browser or when working with anonymous data or data that cannot be associated with a single person. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <span class="uicontrol"> Device Advertising ID</span>: The mobile device identifier. Select this when your data source is a mobile device or Internet enabled device. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <span class="uicontrol"> Cross Device</span>: A customer-provided, authenticated ID. Select this option when you want to create: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a Profile Merge Rule. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> ID Definition</span> </p> </td> 
   <td colname="col2"> <p>The <span class="uicontrol"> ID Definition</span> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by the <span class="keyword"> Adobe Experience Cloud Device Co-op</span> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. Options include: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <span class="uicontrol"> Person:</span> The ID used to define a single person. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <span class="uicontrol"> Household:</span> The ID used to define a group of people. This ID can be mapped to multiple Audience Manager IDs. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Data Export Controls {#section_38F7E2A550A44A079BA8C26148B25349}

[ Data Export Controls ](../../c_features/c_dec.md#concept_155AAFBA7D804467B6F8279D26C9D05C) are optional classification rules you can apply to a data source and destination. They prevent you from sending data to a destination when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL  Data Export Controls]. 


>[!IMPORTANT]
>
>Export restrictions will not work unless you set a matching export label on a destination.



Options include: 


* **[!UICONTROL  No Restriction]**
* **[!UICONTROL  Cannot be tied to personally identifiable information]**
* **[!UICONTROL  Cannot be used for on-site ad targeting]**
* **[!UICONTROL  Cannot be used for off-site ad targeting]**
* **[!UICONTROL  Cannot be used for on-site personalization]**


## Data Source Settings {#section_423704D358D049738DBA4216FEFFF798}

The [!UICONTROL  Data Source Settings] contains the controls and options listed below. Some of these settings have additional sub-options and menu items that you can select to modify a data source. 

**Inbound Data Source Settings** 

Select the **[!UICONTROL  Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL  Inbound]** check box exposes 2 additional groups of controls described below. 



<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Menu Options </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> ID Type</span> </p> </td> 
   <td colname="col2"> <p>The <span class="uicontrol"> Inbound</span> option requires an ID type. Options include: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <span class="uicontrol"> Customer ID</span>: Identifies inbound data with a customer ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <span class="uicontrol"> Audience Manager ID</span>: Identifies inbound data with an <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <span class="uicontrol"> Experience Cloud ID</span>: Identifies inbound data with an Experience Cloud ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> File Format Troubleshooting</span> </p> </td> 
   <td colname="col2"> <p>Select <span class="uicontrol"> Enable file error sampling</span> when you need to troubleshoot problems with inbound file processing. This feature generates an error sample report that shows you file format and syntax errors. </p> <p>See <a href="../../c_features/c_analytics/onboarding-status-report/onboarding-status-report.md#concept_3231613176F44D87AAA05D3528DD294C" format="dita" scope="local"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Other Data Source Settings** 



<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Select When </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Outbound</span> </p> </td> 
   <td colname="col2"> <p>Your data source sends data to a destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Share Enabled</span> </p> </td> 
   <td colname="col2"> <p>Your data source can be shared with other partners. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Use as an Authenticated Profile</span> </p> </td> 
   <td colname="col2"> <p>Your cross-device data source contains and Authenticated ID. An Authenticated ID is collected and synced to an Audience Manager ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). The Authenticated ID can be used to on-board data from other sources which store this ID. It can also be used to link multiple device IDs in Profile Link. </p> <p>This option exposes a text field which lets you rename the data source with an alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../../c_features/profile-link-intro/merge-rules-start/create-profile-merge-rule.md#concept_55706E2521944DF1A5C7B0E19C7436D0" format="dita" scope="local"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Use as a Device Graph</span> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Your consultant will have to provision those companies through our internal processes. </p> <p>This option exposes a text field which lets you rename the data source with an alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../../c_features/profile-link-intro/merge-rules-start/create-profile-merge-rule.md#concept_55706E2521944DF1A5C7B0E19C7436D0" format="dita" scope="local"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Share associated visitor or device IDs with specific Audience Manager Customers</span> </p> </td> 
   <td colname="col2"> <p>Your cross-device data source contains IDs from a device graph. A device graph is a collection of IDs which map to one or more Audience Manager IDs to a cluster. This cluster typically represents a person or larger, household group. Available only to accounts listed as a "Data Provider." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Share associated visitor or device IDs across the Audience Manager Platform</span> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Unique Trait Integration Codes</span> </p> </td> 
   <td colname="col2"> <p>You want to enforce that two traits from the same data source don't have the same integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Unique Segment Integration Codes</span> </p> </td> 
   <td colname="col2"> <p>You want to enforce that two segments from the same data source don't have the same integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

