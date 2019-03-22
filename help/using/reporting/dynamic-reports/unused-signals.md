---
description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Unused Signals Report
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
---

# Unused Signals Report{#unused-signals-report}

This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.

<!-- 

c_unused_signals.xml

 -->

## Unused Signals Report

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

Unused signals consist of data that you collect but have not been mapped to a trait. The [!UICONTROL Unused Signals] report shows data in a table by date, key, value, and frequency count. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

Review this report to help identify orphaned signals that can be mapped to new or existing traits.

>[!NOTE]
>
>Specify a key or value name in the search fields to limit results to specific records.

## Use Cases

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Examples </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Ensure Trait Uniformity or Add Related Values to a Single Key</b> </p> </td> 
   <td colname="col2"> <p>Review the report to account for different value variations for a particular signal. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternatively, you could spot name variants with the report and replace those with a uniform value across all sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Create New Traits</b> </p> </td> 
   <td colname="col2"> <p>Review the report to see what new values get passed in on a particular key. You may want to create new key-value pairs based on these new values. </p> <p> <p>Note:  Check the report bi-weekly for values that change frequently (e.g., shows, campaigns, celebrities, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Find Unmapped Values</b> </p> </td> 
   <td colname="col2"> <p>Review the report for the number 1. The number 1 in an <span class="wintitle"> Unused Signals</span> report represents a null value. This is not necessarily bad. It simply means that a particular key does not have an associated value mapping. When you see a lot of 1 values for an important variable, check with your site team to make sure all your pages are tagged correctly. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices

Run and check the [!UICONTROL Unused Signals] report:

* After you create a trait or update trait rules. This helps ensure your traits and rules are set up properly. The number 1 in results indicates a new trait may not be configured correctly.
* Bi-weekly or monthly. Scheduled reviews help ensure trait mappings are up-to-date.

>[!NOTE]
>
>When searching for unused values in the report, please consider the following particularity. There is a difference in expression between the two examples below:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. In the second case, values different than 23 were sent so key a is not unused.

## Bulk Trait Creation

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
