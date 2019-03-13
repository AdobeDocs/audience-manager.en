---
description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Prefix Requirements for Key Variables
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
---

# Prefix Requirements for Key Variables {#prefix-requirements-for-key-variables}

This article describes the prefixes you must attach to key variables when creating trait rules.

<!-- r_tb_variable_prefixes.xml -->

## Purpose of Key Variable Prefixes

When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. Generally, you can give a variable any name, but data for a rule will not process if the key variable name does not match the variable name in an event call.

## Prefixes for Key Variables

The following table defines the common prefixes used by [!UICONTROL Trait Builder].  

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key variable prefix </th> 
   <th colname="col2" class="entry"> Identifies the variable </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>As customer specific. This is key data sent in from your own properties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>At the <span class="keyword"> Audience Manager</span> level. This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>That contains <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. Includes header parameters such as <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Note: For customers using DIL versions older than 9.0, data collection using the <code> h_referer</code> signal will not work on Safari browsers. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, Safari browsers may classify the demdex.net domain as a tracker and will truncate the referrer on the data collection request to only contain the origin instead of the full URL. See <a href="../../dil/dil-overview.md#section_C781C1F5E2324F618469C124999CC88A">Getting and Implementing DIL Code</a> for the latest DIL version.. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Our <span class="wintitle"> Data Collection Servers</span> allow passing of private parameters. Basically, any parameter that starts with <code> p_</code> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <code> /event?p_age=23</code> and a trait like <code> YoungPeople = p_age &lt; 25</code>, the trait will be realized, but the <code> p_age=23</code> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Basic Information Overview](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Managing Trait Rules](../../features/traits/manage-trait-rules.md#managing-trait-rules)
