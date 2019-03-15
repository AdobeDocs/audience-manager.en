---
description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Billing for Data Feed Providers
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
---

# Billing for Data Feed Providers {#billing-for-data-feed-providers}

Generate an [!DNL Audience Marketplace] billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.

## Download a Billing Report {#download-billing-report}

To download a report:

1. Go to **[!UICONTROL Audience Marketplace > Receivables]**.
1. Click **[!UICONTROL Generate Billing Report]**.

## Report Fields Defined {#report-fields-defined}

A billing report contains the following information.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data Provider PID</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data Provider Name</span></b> </p> </td> 
   <td colname="col2"> <p>Your company or organization name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Buyer PID</span></b> </p> </td> 
   <td colname="col2"> <p>Buyer (subscriber) ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Buyer Name</span></b> </p> </td> 
   <td colname="col2"> <p>The buyer's company or organization name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed ID</span></b> </p> </td> 
   <td colname="col2"> <p>The ID of the data feed </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed Name</span></b> </p> </td> 
   <td colname="col2"> <p>The name of the data feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Plan Use Cases</span></b> </p> </td> 
   <td colname="col2"> <p>Use cases let sellers control how buyers use data. Options include: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segments and overlap </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modeling </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Plan Types for Data Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unit of Measure</span></b> </p> </td> 
   <td colname="col2"> <p>Indicates CPM or flat fee billing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> List Price</span></b> </p> </td> 
   <td colname="col2"> <p>The subscription fee for each data feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Discounted Price</span></b> </p> </td> 
   <td colname="col2"> <p>The subscription fee for a discounted data feed. See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Discounts for Data Providers</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Units</span></b> </p> </td> 
   <td colname="col2"> <p>Varies by feed price type: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Flat fee data feeds: Returns 1 only. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM data feeds: Returns the actual usage amount for CPM data feeds. If a subscriber has not provided impression data for a CPM feed, the Units cell is empty and the Flag cell is set to 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Total Cost</span></b> </p> </td> 
   <td colname="col2"> <p>The amount <span class="keyword"> Audience Manager</span> bills a buyer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Billing Period</span></b> </p> </td> 
   <td colname="col2"> <p> In the report, this is the last day of the previous month. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Entry Date</span></b> </p> </td> 
   <td colname="col2"> <p>The date a buyer entered subscription / usage information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Subscription Start Date</span></b> </p> </td> 
   <td colname="col2"> <p>The date a buyer started their data feed subscription. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Subscription End Date</span></b> </p> </td> 
   <td colname="col2"> <p>The date a buyer ended their data feed subscription. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>For CPM feeds only</i>. Flag options include: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indicates a subscriber has reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indicates a subscriber has not reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Billing and Impression Allocation for CPM Data Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Billing and Impression Allocation for Flat Fee Data Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#concept_FE781C4C5C044C1F986F1AB6BA4E328F)
>* [How to Report CPM Usage](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
