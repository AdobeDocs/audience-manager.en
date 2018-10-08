---
description: Column header labels defined.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Bulk Management Tools Glossary
uuid: 643767b7-1d55-4ced-a1f8-91b1cd004d1d
index: y
internal: n
snippet: y
translate: y
---

# Bulk Management Tools Glossary

Column header labels defined.

<!-- <p>r_bulk_glossary.xml </p> -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools]* are not* supported by [!DNL Audience Manager]. This tool is provided for convenience and as a courtesy only. For bulk changes, we recommend that you work with the [Audience Manager APIs](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_api.html) instead. [RBAC group permissions](../../c_features/c_administration/c_administration.md#concept_A606A162611E4256BB80F60715282296) assigned in the Audience Manager UI are honored in the Bulk Management Tools.

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Column header </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>The ID of a <a href="../../c_features/datasources-list-and-settings.md#concept_DC7CC030739C436C947078C7877C15AD" format="dita" scope="local"> data source</a> you want to return or assign in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../c_features/derived-signals.md#concept_36FF7303F39E4748AC048D08F9E371C6" format="dita" scope="local"> derived signal</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>A brief, informative description that you can give to an object. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>The ID of the <a href="../../c_features/destinations/destinations.md#concept_5BDA346C376C4B719EA394108AB2735A" format="dita" scope="local"> destination</a> you want to map or delete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>A special ID assigned to a segment when it is mapped to a destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>The ID of your segment or trait folder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>The name of the object you're working with. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>The ID of a segment or trait folder that contains other folders. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>Segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Signals are bits of data passed in to <span class="keyword"> Audience Manager</span> based on user activity. These are transmitted as <a href="../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49" format="dita" scope="local"> key-value pairs</a>. The source key is a constant that does not change. It helps categorize the source value which can change. See <a href="../../c_features/derived-signals.md#concept_36FF7303F39E4748AC048D08F9E371C6" format="dita" scope="local"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>The source value is a variable passed in as part a <a href="../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49" format="dita" scope="local"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indicates when a segment can start to be sent to a destination. Uses <tt>yyyy-mm-dd</tt> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">The key used in the derived signal. See <a href="https://marketing.adobe.com/resources/help/en_US/aam/?f=c_tb_derived_signal.html" format="https" scope="external"> Derived Signals</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>The value passed in with a derived signal key. See <a href="https://marketing.adobe.com/resources/help/en_US/aam/?f=c_tb_derived_signal.html" format="https" scope="external"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>An ID passed to a non-cookie based destination. For a cookie-based destination, this is the key in a <a href="../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49" format="dita" scope="local"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>The actual trait or segment rule used to collect data. A bulk request returns the rules created in <span class="keyword"> Audience Manager</span> with the <a href="../../c_features/traits/about-trait-builder.md#concept_BCDC4BCAEB4A4879AFA4A9B98D9ED369" format="dita" scope="local"> trait rule builder</a> or the <a href="../../c_features/c_segments/segment-builder.md#concept_FABA1F399CFD4E83B874043638D0FA54" format="dita" scope="local"> segment rule builder</a>. You can also use these tools to build rules and apply them in bulk when you update a segment or trait. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md#concept_0C752BE1F2E74FEE9611385DE08EB7D2" format="dita" scope="local"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>A string that identifies the trait type. Options include: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <span class="codeph"> RULE_BASED_TRAIT</span> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <span class="codeph"> ON_BOARDED_TRAIT </span> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <span class="codeph"> SEGMENT</span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel fired by DIL when a user qualifies for a segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>The key in a <a href="../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49" format="dita" scope="local"> key-value pair</a> passed to a cookie destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

