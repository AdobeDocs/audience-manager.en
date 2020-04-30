---
description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Visitor Authentication States in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
---

# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` identifies visitors according to their [authentication status](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] handles the realized traits differently, depending on the authentication status passed in the call and the [Profile Merge Rule](../features/profile-merge-rules/merge-rules-dashboard.md) you use for segmentation.

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Request value </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Read</b> information from the authenticated profile </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Write</b> new traits to the authenticated profile </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Yes, if the Authenticated Option Merge Rule = "Last Authenticated Profiles". </p> </td> 
   <td colname="col3" morerows="1"> <p>No, the trait data is added to the device profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, if the Authenticated Option Merge Rule = "Current Authenticated Profiles" or "No Authenticated Profile". </p> </td> 
  </tr> 
 </tbody> 
</table>

Sample call (the request value corresponding to the authentication status is highlighted):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Request value </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Read</b> information from the authenticated profile </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Write</b> new traits to the authenticated profile </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Yes, if the Authenticated Option Merge Rule = "Current Authenticated Profiles" or "Last Authenticated Profiles". </p> </td> 
   <td colname="col3" morerows="1"> <p>Yes, the trait data is added to the authenticated profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, if the Authenticated Option Merge Rule = "No Authenticated Profile". </p> </td> 
  </tr> 
 </tbody> 
</table>

Sample call (the request value corresponding to the authentication status is highlighted):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Request value </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Read</b> information from the authenticated profile </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Write</b> new traits to the authenticated profile </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Yes, if the Authenticated Option Merge Rule = "Last Authenticated Profiles" </td> 
   <td colname="col3" morerows="1"> <p>No, the trait data is written to the device profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, if the Authenticated Option Merge Rule = "Current Authenticated Profiles" or "No Authenticated Profile" </td> 
  </tr> 
 </tbody> 
</table>

Sample call (the request value corresponding to the authentication status is highlighted):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] performs an ID synchronization between [CID and UUID](../reference/ids-in-aam.md) in all three cases.

>[!MORELIKETHIS]
>
>* [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)
