---
description: Describes the variation in unique user totals between reports for the same trait and time period.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Counting Unique Users in Overlap and General Reports
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
---
# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

This page describes the variation in unique user totals between reports for the same trait and time period.

<!-- 

c_unique_user_counts.xml

 -->

## Overlap Report: Unique User Count

The overlap reports count users as unique when they qualify for a trait:

* During the selected time interval for the report.
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* If they're seen as active in our system (i.e, qualified for any other trait, had an ID sync, etc.) within the past 60 days.

## General Report: Unique User Count

The General report counts site visitors as unique if they qualified for the trait during the selected time period.

>[!MORELIKETHIS]
>
>* [Interactive Reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [General Reports](../reporting/general-reports.md#general-reports-overview)
