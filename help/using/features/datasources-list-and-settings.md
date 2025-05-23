---
description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Data Sources List and Settings
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
---
# [!UICONTROL Data Sources] List and Settings {#data-sources-list-and-settings}

View a list of your currently configured [!UICONTROL data sources], add new [!UICONTROL data sources], and edit existing [!UICONTROL data sources].

You can also manage [!UICONTROL data sources] using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] List View {#list-view}

The [!UICONTROL Data Sources] dashboard is a centralized workspace for managing data sources.

The [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contains features and tools that help you:

* See all your existing [!UICONTROL data sources], including each data source's description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* Search for [!UICONTROL data sources] by name.
* Create, edit, and delete [!UICONTROL data sources].

## [!DNL Data Source] Settings and Menu Options {#settings-menu-options}

The settings in the different sections of the [!UICONTROL Data Source] management interface identify your [!DNL data source], determine how it is used or shared, and let you enable error reporting for the [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Details {#details}

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Menu Options </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID Type</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: The cookie ID that identifies a device. You would select this when your data source is a web browser or when working with anonymous data or data that cannot be associated with a single person. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Device Advertising ID</span></b>: The mobile device identifier. Select this when your data source is a mobile device or Internet enabled device. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross Device</span></b>: A customer-provided, authenticated ID. Select this option when you want to create: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by a third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID Definition</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> ID Definition</span></b> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by a third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. Options include: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> The ID used to define a single person. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Household:</span></b> The ID used to define a group of people. This ID can be mapped to multiple Audience Manager IDs. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Data Export Controls](../features/data-export-controls.md) are optional classification rules you can apply to a [!UICONTROL data source] and [!UICONTROL destination]. They prevent you from sending data to a [!UICONTROL destination] when that action violates a data privacy or use agreement. Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Export restrictions will not work unless you set a matching export label on a [!UICONTROL destination].

Options include:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Settings {#data-source-settings}

The [!UICONTROL Data Source Settings] contains the controls and options listed below. Some of these settings have additional sub-options and menu items that you can select to modify a data source.

### [!UICONTROL Inbound Data Source] Settings

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

>[!NOTE]
>
>The **[!UICONTROL Inbound]** check box is only meant to display or hide the [!UICONTROL data source] controls described below. Unchecking the **[!UICONTROL Inbound]** option does not affect data ingestion in any way. Your onboarded data will be processed regardless of this option being checked.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Menu Options </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID Type</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> Inbound</span></b> option requires an ID type. Options include: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Customer ID</span></b>: Identifies inbound data with a customer ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: Identifies inbound data with an <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifies inbound data with an <span class="keyword"> Experience Cloud</span> ID. See <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> File Format Troubleshooting</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. This feature generates an error sample report that shows you file format and syntax errors. </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Other [!UICONTROL Data Source] Settings

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Select When </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Outbound</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source sends data to a destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Share Enabled</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source can be shared with other partners. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Use as an Authenticated Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Your cross-device data source contains an Authenticated ID. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). The Authenticated ID can be used to on-board data from other sources which store this ID. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>This option exposes a text field which lets you rename the data source with an alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Use as a Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Your consultant will have to provision those companies through our internal processes. </p> <p>This option exposes a text field which lets you rename the data source with an alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Share associated visitor or device IDs with specific Audience Manager Customers</span></b> </p> </td> 
   <td colname="col2"> <p>Your cross-device data source contains IDs from a device graph. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. This cluster typically represents a person or larger, household group. Available only to accounts listed as a "Data Provider." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Share associated visitor or device IDs across the Audience Manager Platform</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Data retention for inactive Customer IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Allows you to set the data retention period for inactive Customer IDs. This determines how long Audience Manager keeps Customer IDs in our database after they were last seen on the Audience Manager platform.</p> <p>The default value is 24 months (720 days). The minimum value you can set is 1 month and the maximum value is 5 years. Note that we count all months as 30-days.</p> <p>Audience Manager runs a process that deletes inactive Customer IDs once a week, in accordance with the data retention you set for inactive Customer IDs.</p> <p>Audience Manager runs a process that deletes inactive Customer IDs once a week, in accordance with the data retention you set for inactive Customer IDs.</p> <p><b>Note</b>: This control is available only for cross-device data sources. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Trait Integration Codes</span></b> </p> </td> 
   <td colname="col2"> <p>You want to enforce that two traits from the same data source don't have the same integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Segment Integration Codes</span></b> </p> </td> 
   <td colname="col2"> <p>You want to enforce that two segments from the same data source don't have the same integration code. </p> </td> 
  </tr>
 </tbody>
</table>
