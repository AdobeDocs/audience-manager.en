---
description: A [!DNL key-value pair] consists of related elements: A key, which is a constant that defines the data set (e.g., gender, color, price) and a value, which is a variable that belongs to the set (e.g., male/female, green, 100). Destination Builder sends data formatted as key-value pairs.
solution: Audience Manager
title: Standard and Serial [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
---
# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

A key-value pair consists of related elements: A key, which is a constant that defines the data set (e.g., gender, color, price) and a value, which is a variable that belongs to the set (e.g., male/female, green, 100). [!UICONTROL Destination Builder] sends data formatted as key-value pairs.

## Basic Key-Value Pairs {#basic-key-value-pairs}

Fully formed, a basic set of key-value pair could look like these:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **Standard key-value pairs:** Formats destination data into separate key-value pairs. Each key is stated explicitly, even when used again to define a different value.
* **Serialized key-value pairs:** Condenses multiple values into a single key-value pair. In a serialized key-value pair, a special indicator separates the values within the key-value set.

Both standard and serialized key-values can contain single or multiple values. The following table provides examples of standard and serial key-value formats.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatting </th>
   <th colname="col2" class="entry"> Single Key-Value Pairs </th>
   <th colname="col3" class="entry"> Multiple Key-Value Pairs </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Serialized</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. These become particularly important when you send segments to a destination in a serial format. Serialization lets you pass in multiple values with a single key and combine key-value pairs. Delimiters and separators are defined as follows:

* **Key-value separator:** Separates a key and value within a key-value pair.
* **Key-value delimiter:** Separates sets of key-value pairs.
* **Serial separator:** Separates multiple values within sets of serialized key-value pairs.

## Examples {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. Let's take a look at some examples of each type.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key-Value Pair Examples </th> 
   <th colname="col2" class="entry"> Example </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard single key</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>A simple set of key-value pairs. The example contains these elements: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Key: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Values: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Separator: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Key-value delimiter: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Multiple key-value pairs</b> (non-serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>A set of multiple key-value pairs that pass in values with separate key-value sets. The example contains these elements: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Keys: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Values: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separator: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Key-value delimiter: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Serial single key</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>A key-value set that passes in multiple values with a single key. Because this key has multiple values, it is known as a serialized key-value pair. The example contains these elements: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Key: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Values: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separator: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Serial separator: semi-colon </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Multiple key-value pairs</b> (serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>A set of multiple key-value pairs that pass in multiple values on separate keys. The example contains these elements: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Keys: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Values: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Separator: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimiter: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Serial separator: semi-colon </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

A serialized destination combines multiple traits into a single string and sends that information to a destination.

<!-- c_dest_serialized.xml -->

Serialized data transmission helps improve efficiency because multiple traits fire sequentially, rather than in parallel. This provides the destination server with enough time to receive, process, and return data before responding to additional requests.

### Supported Destinations

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. Obtain the information about macro placement from your destination partner. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.
