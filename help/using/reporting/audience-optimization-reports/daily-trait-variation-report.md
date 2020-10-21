---
description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Daily Trait Variation Report
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
---

# Daily Trait Variation Report {#daily-trait-variation-report}

This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.

>[!NOTE]
>
>The Daily Trait Variation report in Audience Manager adheres to RBAC principles. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

Standard deviation measures the amount of variation or dispersion from the mean (or average/expected value). A low standard deviation indicates that the data points tend to be very close to the mean. A high standard deviation indicates that the data points are spread out over a large range of values.

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. A color-coded bar chart displays at the bottom of the list that provides a visual representative of the range of standard deviation for all traits across all selected dates. The black vertical line indicates the mean.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. Click any trait to access a pop-up dialog box that lets you select from the following options:

* **Keep Only:** Removes all other traits from the report and displays data for this trait only. 
* **Exclude:** Removes this trait from the report and displays data for all other traits. You can exclude multiple traits. 
* **View Data:** Lets you display data for that row. You can also download all rows as a text file.

The [!UICONTROL Standard Deviation] column displays color-coded bar charts that display the standard deviation for each trait over the selected interval. Red bars indicate traits with a negative standard deviation (data points tend to be below the mean). Green bars indicate traits with a positive standard deviation (data points tend to be above the mean). Mouse over any bar to display a pop-up dialog box with more information and options to keep or exclude that trait and view more information.

Icons display at the bottom of the report that let you export data in various formats, revert any changes you might have made to the report (such as excluding traits), enable or disable automatic updates, and refresh the report's data. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Use Cases {#use-cases}

**Example #1**: this report can be highly useful in situations where you have traits with a high seasonality level. For instance, let's say your online store is testing seasonal promotions of various types and prices. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. This can suggest that your visitors are looking for the products mentioned in your seasonal promotion. To capitalize on this trend, you can then invest more effort into targeting creatives for that specific product category on visitors that are interested in them.

**Example #2**: this report can help you identify targeting anomalies related to tagging issues or trait misconfigurations. Imagine you've defined the following trait based on the categories of your online store:

* `productPage == "smartphones"`

Due to a reconfiguration of your store, you're splitting the smartphones page into multiple pages, based on brand names. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven't updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* productPage == "samsung"
* productPage == "apple"
* productPage == "huawei"

Once you do this, you'll see your audience qualifying for the newly created traits.
