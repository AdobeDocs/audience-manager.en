---
description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Prefix Requirements for Key Variables
uuid: ae034afd-901f-42c4-a372-f8648f3a47f7
index: y
internal: n
snippet: y
translate: y
---

# Prefix Requirements for Key Variables

This article describes the prefixes you must attach to key variables when creating trait rules.


>
>
>**Purpose of Key Variable Prefixes** 
>
>
>When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. Generally, you can give a variable any name, but data for a rule will not process if the key variable name does not match the variable name in an event call. 
>
>
>**Prefixes for Key Variables** 
>
>
>The following table defines the common prefixes used by [!UICONTROL Trait Builder]. 
>
>
><table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
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
   <td colname="col2"> <p>At the <span class="keyword"> Audience Manager</span> level. This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../c_api/dcs-intro/dcs-api-reference/dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5" format="dita" scope="local"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> h_</span> </td> 
   <td colname="col2"> <p>That contains <a href="http://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. Includes header parameters such as <span class="codeph"> referer</span>,<span class="codeph"> IP</span>, <span class="codeph"> accept-language</span>, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> p_</span> </td> 
   <td colname="col2"> <p>Our <span class="wintitle"> Data Collection Servers</span> allow passing of private parameters. Basically, any parameter that starts with <span class="codeph"> p_</span> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <span class="codeph"> /event?p_age=23</span> and a trait like <span class="codeph"> YoungPeople = p_age &lt; 25</span>, the trait will be realized, but the <span class="codeph"> p_age=23</span> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>>
>
>[!MORE_LIKE_THIS]
>
>* [Basic Information Overview](create-onboarded-rule-based-traits.md#concept_D80233EF56764376B0F4C4FF882BAD2E)
>* [Managing Trait Rules](manage-trait-rules.md#concept_3A566134D5704002B3713D0909C94389)
