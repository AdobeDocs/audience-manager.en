---
description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: Why did my Onboarded trait populations drop to 0 around October 15th?
feature: support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
---
# Why did my Onboarded trait populations drop to 0 around October 15th? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Question

Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher. Why did this happen?

![Image of Device ID drop](assets/device_id_populationdrop.png)

## Answer

On October 15th, an update to Audience Manager's Profile Merge Rule functionality was changed to where Onboarded data keyed off of a CRM ID uploaded to a Cross Device Data Source are no longer being realized against device ids.  Previously Audience Manager was realizing against both the Cross Device ID (or CRM ID) as well as copying those realizations to associated Audience Manager UUIDs (Device IDs).  The change was made to more accurately reflect the nature of the trait data and the profiles being realized.

To view the trait realizations, please select "Cross-Device ID" option from the drop down in the top right hand corner of the Trait view.

![View Realizations by Cross-device ID](assets/deviceid-crossdevice.png)
