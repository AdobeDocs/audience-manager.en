---
description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Prefix Requirements for Key Variables
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
index: y
internal: n
snippet: y
---

# Prefix Requirements for Key Variables{#prefix-requirements-for-key-variables}

This article describes the prefixes you must attach to key variables when creating trait rules.

<!-- 

r_tb_variable_prefixes.xml

 -->

**Purpose of Key Variable Prefixes**

When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. Generally, you can give a variable any name, but data for a rule will not process if the key variable name does not match the variable name in an event call.

**Prefixes for Key Variables**

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
   <td colname="col1"><span class="codeph"> c_</span> </td> 
   <td colname="col2"> <p>As customer specific. This is key data sent in from your own properties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> d_</span> </td> 
   <td colname="col2"> <p>At the <span class="keyword"> Audience Manager</span> level. This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../c-api/dcs-intro/dcs-api-reference/dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> h_</span> </td> 
   <td colname="col2"> <p>That contains <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. Includes header parameters such as <span class="codeph"> referer</span>,<span class="codeph"> IP</span>, <span class="codeph"> accept-language</span>, etc. </p> <p> <p>Note: Data collection using the <span class="codeph"> h_referer</span> signal will not work on Safari browsers. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, Safari browsers may classify the demdex.net domain as a tracker and will truncate the referrer on the data collection request to only contain the origin instead of the full URL. We are working on a solution and will update this article accordingly. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> p_</span> </td> 
   <td colname="col2"> <p>Our <span class="wintitle"> Data Collection Servers</span> allow passing of private parameters. Basically, any parameter that starts with <span class="codeph"> p_</span> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <span class="codeph"> /event?p_age=23</span> and a trait like <span class="codeph"> YoungPeople = p_age &lt; 25</span>, the trait will be realized, but the <span class="codeph"> p_age=23</span> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Basic Information Overview](../../c-features/traits/create-onboarded-rule-based-trait-details-page.md)
>* [Managing Trait Rules](../../c-features/traits/manage-trait-rules.md#concept_3A566134D5704002B3713D0909C94389)
