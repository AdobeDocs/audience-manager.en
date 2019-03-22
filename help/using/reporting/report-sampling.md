---
description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Data Sampling and Error Rates in Selected Audience Manager Reports
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
---

# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. The sampled data ratio is 1:54. For reports that use sampled data, this means your results are based on 1 record out of every set of 54 records.

These reports use sampled data because they need a tremendous amount of computing power to generate results. Sampling helps strike a balance between reduced computational demands, maintaining system performance, and providing accurate results.

Reports that use sampling exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 over a 14-day period.
* Segments: 70,000 real-time users over a 14-day period.

## Error Rates {#error-rates}

Errors can occur in reports that generate overlap data. An error is defined as the percentage of records that:

* Should not have been included in a report but were added anyway. 
* Should have been included in a report but were left out.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Data sets that have a lot of records generate fewer errors than sets with a small number of records. Let's look at this assertion in a more quantitative manner. As shown in the following table, for a set number of records, 95% of your report results will be below a specific error rate.

|Number of Records|Error Rate|
|--- |--- |
|500 - 1,000|95% are under a 42% error rate.|
|1,000 - 1,500|95% are under a 34% error rate.|
|10,000 - 50,000|95% are under a 14% error rate.|
|50,000|95% are under a 6% error rate.|
|100,000|95% are under a 4% error rate.|
|500,000 (or more)|95% are under a 2% error rate.|

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
