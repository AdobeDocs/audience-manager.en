---
description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Visitor Authentication States in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
---
# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` identifies visitors according to their [authentication status](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] handles the realized traits differently, depending on the authentication status passed in the call and the [Profile Merge Rule](../features/profile-merge-rules/merge-rules-dashboard.md) you use for segmentation.

## Authentication Status: UNKNOWN {#auth-status-unknown}

|Request value|Read information from the authenticated profile|Write new traits to the authenticated profile|
|---|---|---|
|0|<ul><li>Yes, if the [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, if the [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] or [!UICONTROL No Authenticated Profile].</li></ul>|No, the trait data is added to the device profile.|

Sample call (the request value corresponding to the authentication status is highlighted):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

|Request value|Read information from the authenticated profile|Write new traits to the authenticated profile|
|---|---|---|
|1|<ul><li>Yes, if the [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] or [!UICONTROL Last Authenticated Profiles].</li><li>No, if the [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul>|Yes, the trait data is added to the authenticated profile.|

Sample call (the request value corresponding to the authentication status is highlighted):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

|Request value|Read information from the authenticated profile|Write new traits to the authenticated profile|
|---|---|---|
|2|<ul><li>Yes, if the [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, if the [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] or [!UICONTROL No Authenticated Profile].</li></ul>|No, the trait data is written to the device profile.|

Sample call (the request value corresponding to the authentication status is highlighted):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] performs an ID synchronization between [CID and UUID](../reference/ids-in-aam.md) in all three cases.

>[!MORELIKETHIS]
>
>* [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)
