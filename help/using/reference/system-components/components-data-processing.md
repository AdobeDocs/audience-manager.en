---
description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Data Processing Components
uuid: d458d869-7a23-4016-871d-0b994cf4af06
---

# Data Processing Components{#data-processing-components}

Data processing components include Hadoop, Snowflake, SOLR, and Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager uses the following components to process data:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. Other important Hadoop elements include:

* **Hive:** A data warehouse for Hadoop. Hive manages ad hoc queries to the data stored in Hadoop. 

* **HBase:** A very large Hadoop database. It processes and manages inbound and outbound data, trait rules, algorithmic modeling information, and performs many other functions related to storing and moving data to different systems.

Customers do not have direct access to these systems. However, customers do work with them indirectly as these components store important data about their site visitors.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) is a massive cloud database. It provides data to many of the dashboard graphs and their related text boxes that display the % change for each item in the graph. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [Daily Trait Variation Report](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md) 
* [Delivery and Performance Report](/help/using/reporting/dynamic-reports/delivery-performance-report.md) 
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report). 
* [Unused Signals Report](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR is an open-source database and server system from Apache. It provides robust and fast search capabilities over our large data sets. As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR is ideal for this role because of its speed. For example, SOLR is able to update the historic size data as you build rules and add new traits to a segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] uses [Tableau](https://www.tableausoftware.com/) to display data in the [Interactive Reports](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) and the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md). The interactive reports display performance and overlap data for traits and segments. Instead of using numbers arranged in columns and rows, they return data using different shapes, colors, and sizes. Additionally, you can choose individual or groups of data points and drill down into the report results for more details. These visualization techniques and report interactivity help make large amounts of numeric data easier to understand.



![](assets/advertiser_analytics.png)

