---
description: This page includes the top issues reported to Audience Manager Customer Care.
seo-description: This page includes the top issues reported to Audience Manager Customer Care.
seo-title: Customer Care - Most Frequently Reported Issues
solution: Audience Manager
title: Customer Care - Most Frequently Reported Issues
---

# Customer Care - Most Frequently Reported Issues{#most-frequent-issues}

This page includes the top issues reported to Audience Manager Customer Care in 2019.

## Why are our Read-Only users able to create, edit or delete traits and segments?

**Question**

Why are our Read-Only users able to create, edit or delete traits and segments?

**Answer**

On top of creating groups and permissions in the administration section, you need to contact Customer Care (amsupport@adobe.com) so a representative can enable Role Based Access Controls (RBAC) for your account.

<br>&nbsp;

## Why did my Onboarded trait populations drop to 0 around October 15th? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.

![Image of Device ID drop](/help/using/support-issues/assets/device_id_populationdrop.png)

**Answer**

On October 15th, an update to Audience Manager's Profile Merge Rule functionality was changed to where Onboarded data keyed off of a CRM ID uploaded to a Cross Device Data Source are no longer being realized against device ids.  Previously Audience Manager was realizing against both the Cross Device ID (or CRM ID) as well as copying those realizations to associated Audience Manager UUIDs (Device IDs).  The change was made to more accurately reflect the nature of the trait data and the profiles being realized.

To view the trait realizations, please select "Cross-Device ID" option from the drop down in the top right hand corner of the Trait view.

![View Realizations by Cross-device ID](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br>&nbsp;

## Why do my traits or segments not show up in the Overlap Reports page?

Explanation for why traits and segments might not show up in the Overlap Reports page.

**Question**

Why don't users see certain traits and segments listed in the overlap reports page when attempting to run an overlap report?

**Answer**

A minimum unique visitor requirement needs to be met in order for a trait or segment to be listed in the overlap reports.


* For Traits: 28000 over 14-day period
* For Segments: 70000 real-time users over 14-day period

More details about this can be found on the page [Data Sampling and Error Rates in Selected Audience Manager Reports](/help/using/reporting/report-sampling.md).