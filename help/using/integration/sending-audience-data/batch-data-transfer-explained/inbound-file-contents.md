---
description: Required fields, syntax, and rules you should follow when formatting an inbound trait data file.
seo-description: Required fields, syntax, and rules you should follow when formatting an inbound trait data file.
seo-title: Inbound Data File Contents  Syntax, Invalid Characters, Variables, and Examples
solution: Audience Manager
title: Inbound Data File Contents  Syntax, Invalid Characters, Variables, and Examples
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
---

# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Required fields, syntax, and rules you should follow when formatting an inbound trait data file.

## File Content Syntax {#section_524652571283434B93EF2BA5AEC2962B}

Fields in the inbound data file must appear in the order shown below. In this example, the `<` `>` symbols have been added to help separate each element visually. You do not need to include these in your data file.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

>[!NOTE]
>
>We have a limit of 200 lines we can process for each user ID sent in the inbound data file. For example, if you send 300 lines for a user ID, the first 200 lines are kept and the additional 100 lines are discarded. In the example below, you're good because you are sending 3 lines each for user ID 1 and user ID 2. We don't enforce a limit on the number of traits or key-value pairs you include in a line. >
>```>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```>

## File Variables Defined {#section_D024F453127141B6852B6CFB7F5CD2C8}

The table lists and defines the variables used in a properly formatted inbound data file. *Italics* indicates a variable placeholder.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>A User ID can be: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">A unique user ID assigned by <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">A mobile Android or iOS device ID in its original, unmodified form as exposed by the mobile operating system. </li> 
     </ul> </p> <p>For mobile IDs: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA format: IDs must be upper case and not hashed. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android format: IDs must be lower case and not hashed. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separate the User ID and trait IDs with a single tab delimiter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager </span> trait ID. We ask that you include <i>only onboarded traits</i> in inbound data files. We do not process any other trait types in the inbound data transfer. </p> <p> <p>Note:  The Trait ID can be found by using the GET method that returns details about all your traits. For more information, see <a href="../../../api/rest-api-main/api-traits.md#concept_9DDE7873366644E38E2C58F2CAE8B62D"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#section_0D84D4DD995D444598AF8AE9FC8A3810}

The following table describes the prefixes that identify trait names or IDs in an inbound data file. See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#section_9C29AF9142B2426BA7209E1281AE4C36) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefix </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>The <code> d_sid </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. This is the same ID that's shown in the user interface. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md#concept_9DDE7873366644E38E2C58F2CAE8B62D"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. The <code> d_unsid </code> prefix is ignored in an <code> overwrite </code> file. </p> <p>The <code> d_unsid= </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. This is the same ID that's shown in the user interface. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md#concept_9DDE7873366644E38E2C58F2CAE8B62D"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Trait rules </a> let you set criteria for trait qualification. If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>For example, say you create these 3 trait rules: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. This lets you create a simpler trait list in the data file. And, you do not need to include the <code> ic </code> prefix. As a result, the contents of your data file could look like this: </p> <p>
     <codeblock> 
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <varname>
        user&amp;nbsp;ID 
      </varname>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Key-value pairs </p> </td> 
   <td colname="col2"> <p>Trait data can be formatted as key-value pairs using alphanumeric strings. There are several ways of formatting key-value pairs, as shown below: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul> 
<codeblock> "age"="32" </codeblock> , <codeblock> "gender"=m </codeblock> , <codeblock> model = "pickup truck" </codeblock> , <codeblock> product = tablet </codeblock> are all examples of correctly formatted key-value pairs. </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#section_A52AFA31CCA54EF2A89CEF17BFCCB879}

### Trait IDs

Trait IDs consist only of numerical characters. We ask that you include *only onboarded traits* in inbound data files. We do not process any other trait types in the inbound data transfer.

### User IDs

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID Type </th> 
   <th colname="col2" class="entry"> Requirement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>Do not</i> use an encoded colon ( <code> %3A </code>) or unencoded colon ( : ) symbol in DPUUIDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile iOS (IDFA) or Android device ID </p> </td> 
   <td colname="col2"> <p>Mobile device IDs must be strictly formatted as shown here: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA format: IDs must be upper case and not hashed. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android format: IDs must be lower case and not hashed. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Key-Value Pairs

Improperly formatted value names in a key-value pair also cause problems. Follow these rules when creating or naming the value in a key-value pair:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Character </th> 
   <th colname="col2" class="entry"> Requirement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Quote character (") </p> </td> 
   <td colname="col2"> <p>You can use the quote character in the key and in the value part of key-value pair, like so: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dash character (-) </p> </td> 
   <td colname="col2"> <p>We ignore dash signs at the start of keys. For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Do not</i> use <code> TAB </code> instead of empty values in key-value pairs. Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#section_9C29AF9142B2426BA7209E1281AE4C36}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data File Format </th> 
   <th colname="col2" class="entry"> Description and Example </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>This data file shows a user qualified for traits 24, 26, 27 and has been removed from trait 28 and 29. </p> <p> 
     <codeblock>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </codeblock> </p> <p>Note:  <p>Instead of using d_unsid, you can also remove traits from user profiles by using the following syntax: </p> <p> 
      <codeblock>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </codeblock> </p> <p> 
      <codeblock>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </codeblock> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. As such, you can add them to the data file separated by commas as shown. A tab separates the UUID and the trait IDs. The <code> ic </code> prefix is not required in the file. </p> <p><b>Numeric IDs</b> </p> <p> 
     <codeblock spectitle="Numeric IDs">
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </codeblock> </p> <p><b>String IDs</b> </p> <p> 
     <codeblock spectitle="String IDs">
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With key-value pairs </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <codeblock>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Download](https://marketing.adobe.com/resources/help/en_US/aam/downloads/ftp_dpm_1234_1445374061.overwrite) the sample data file if you need additional examples. The download file has a `.overwrite` file extension. You can open it with a simple text editor.

## Examples Matrix {#section_BA72EA253B3E418AA8F597B1BC73360A}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8) and the method by which you want to add traits to profiles. 

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID Type / Operation </th> 
   <th colname="col2" class="entry"> Use d_sid to add traits to a user profile </th> 
   <th colname="col3" class="entry"> Use d_unsid to remove traits from a user profile </th> 
   <th colname="col4" class="entry"> Send in key-value pairs to add traits to a user profile </th> 
   <th colname="col5" class="entry"> Use the ic prefix to add traits to a user profile </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_2E62E4E7F46448268C9EB9AEB9E60D3F"> Example 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_C16FCBA11ECE40BA98E8774ABB7A66A4"> Example 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_87901E3B17A444C0B033FABCBA2C0D2B"> Example 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_1DF79B9D7A9840CBBD51C2360B3CBDE9"> Example 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID for Android Devices </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_7857F8C615554FBC9FBA2084C64EEBDD"> Example 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_F634761D66C24D849DCEF6919482B30D"> Example 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_4870547D5808450CAAE2648CDB64F561"> Example 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_5FB2F32FF7324BE0B8697784031680F4"> Example 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA for iOS devices </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_7073A4D3DC9F4CA0B464F83933509410"> Example 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_2F02A355D1E4452AB9C85B41FF6F4436"> Example 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_6698940C1F87453A9C21D8A08DC21B25"> Example 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_72EFCD3713F74A91A8B37A5046CDE532"> Example 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Your own CRM ID (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_31EA1C2A9B3A4A75B00B648DDA65635B"> Example 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_3DAA1D2CDD274BD2BBAAAA62C50412EC"> Example 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_21B159FD9EC5455B99A6339CB497644B"> Example 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example_5832A7F48BB747E1994C4FEFE68D5640"> Example 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example_2E62E4E7F46448268C9EB9AEB9E60D3F}

Use trait IDs to send trait qualification information for Audience Manager UUIDs.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example_C16FCBA11ECE40BA98E8774ABB7A66A4}

Use trait IDs to send trait disqualification information for Audience Manager UUIDs.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

or 

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

or 

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 3 {#example_87901E3B17A444C0B033FABCBA2C0D2B}

Send in key-value pairs to add trait qualification information for Audience Manager UUIDs.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

or 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example_1DF79B9D7A9840CBBD51C2360B3CBDE9}

Use the ic prefix to send trait qualification information for Audience Manager UUIDs.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

or 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example_7857F8C615554FBC9FBA2084C64EEBDD}

Use trait IDs to send trait qualification information for Android devices.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example_F634761D66C24D849DCEF6919482B30D}

Use trait IDs to send trait disqualification information for Android devices.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

or 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

or 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 7 {#example_4870547D5808450CAAE2648CDB64F561}

Send in key-value pairs to add trait qualification information for Android devices.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

or 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example_5FB2F32FF7324BE0B8697784031680F4}

Use the ic prefix to send trait qualification information for Android devices.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

or 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example_7073A4D3DC9F4CA0B464F83933509410}

Use trait IDs to send trait qualification information for iOS devices.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example_2F02A355D1E4452AB9C85B41FF6F4436}

Use trait IDs to send trait disqualification information for iOS devices.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

or 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

or 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Example 11 {#example_6698940C1F87453A9C21D8A08DC21B25}

Send in key-value pairs to add trait qualification information for iOS devices.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

or 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example_72EFCD3713F74A91A8B37A5046CDE532}

Use the ic prefix to send trait qualification information for iOS devices.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

or 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example_31EA1C2A9B3A4A75B00B648DDA65635B}

Use trait IDs to send trait qualification information for DPUUIDs.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example_3DAA1D2CDD274BD2BBAAAA62C50412EC}

Use trait IDs to send trait disqualification information for DPUUIDs.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

or 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

or 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 15 {#example_21B159FD9EC5455B99A6339CB497644B}

Send in key-value pairs to add trait qualification information for DPUUIDs.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

or 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example_5832A7F48BB747E1994C4FEFE68D5640}

Use the ic prefix to send trait qualification information for DPUUIDs.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

or 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_LIKE_THIS]
>
>* [Trait Builder](../../../features/traits/about-trait-builder.md#concept_BCDC4BCAEB4A4879AFA4A9B98D9ED369)
