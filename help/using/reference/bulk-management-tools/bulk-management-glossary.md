---
description: Column header labels defined.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Bulk Management Tools Glossary
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: baaam
exl-id: 036d16c7-1546-4539-a318-455b98e10026
---
# Bulk Management Tools Glossary{#bulk-management-tools-glossary}

Column header labels defined.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[RBAC group permissions](../../features/administration/administration-overview.md) assigned in the [!DNL Audience Manager] UI are honored in the [!UICONTROL Bulk Management Tools].

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
   <td colname="col2"> <p>The ID of a <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> you want to return or assign in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> derived signal</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>A brief, informative description that you can give to an object. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>The ID of the <a href="../../features/destinations/destinations.md"> destination</a> you want to map or delete. </p> </td> 
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
   <td colname="col2"> <p>Signals are bits of data passed in to <span class="keyword"> Audience Manager</span> based on user activity. These are transmitted as <a href="../../reference/key-value-pairs-explained.md"> key-value pairs</a>. The source key is a constant that does not change. It helps categorize the source value which can change. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>The source value is a variable passed in as part a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indicates when a segment can start to be sent to a destination. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">The key used in the derived signal. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>The value passed in with a derived signal key. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>An ID passed to a non-cookie based destination. For a cookie-based destination, this is the key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>The actual trait or segment rule used to collect data. A bulk request returns the rules created in <span class="keyword"> Audience Manager</span> with the <a href="../../features/traits/about-trait-builder.md"> trait rule builder</a> or the <a href="../../features/segments/segment-builder.md"> segment rule builder</a>. You can also use these tools to build rules and apply them in bulk when you update a segment or trait. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>A string that identifies the trait type. Options include: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel fired by DIL when a user qualifies for a segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>The key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a> passed to a cookie destination. </p> </td> 
  </tr> 
 </tbody> 
</table>
