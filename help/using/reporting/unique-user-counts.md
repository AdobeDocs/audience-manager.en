---
description: Describes the variation in unique user totals between reports for the same trait and time period.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Counting Unique Users in Overlap and General Reports
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
    internal-label: Reporting
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
    internal-label: Overlap Reports
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
    internal-label: Reporting reference
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
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
