---
description: The Destination landing page lists all of your URL, cookie, and server-to-server destinations. It provides features that let you create, edit, search for, and report on destinations. The landing page is located in Audience Data > Destinations.
seo-description: The Destination landing page lists all of your URL, cookie, and server-to-server destinations. It provides features that let you create, edit, search for, and report on destinations. The landing page is located in Audience Data > Destinations.
seo-title: Manage Destinations
solution: Audience Manager
title: Manage Destinations
uuid: 6b66ff42-0075-49a7-a58f-7f8ea2295fdc
---

# Manage Destinations {#manage-destinations}

The [!UICONTROL Destination] landing page lists all of your [!DNL URL], cookie, and server-to-server destinations. It provides features that let you create, edit, search for, and report on destinations. The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

The default landing page lists and helps you manage all of your destinations. You can create, edit, and search for destinations here.

![](assets/destination_landing1.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

Slide the **[!UICONTROL Show Only Addressable Audience Metrics]** toggle to see audience data and match rates for your server-to-server destinations. When enabled, this feature:

* Lets you filter the report to return audience data and match rates for fixed time intervals.
* Returns data for server-to-server destinations only. Cookie and [!DNL URL] destinations are excluded from the list. Slide the toggle again to return to the default view.

![](assets/destination_landing2.png)

>[!MORE_LIKE_THIS]
>
>* [Addressable Audiences](../../features/addressable-audiences.md#concept_8E0BAEF0978F4968B21482E79E601889)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] lets you create cookie-based or [!DNL URL] destinations. You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder] is located in **[!UICONTROL Audience Data > Destinations]**.

## Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consists of the following sections and settings:  

|[!UICONTROL Destination Builder] Section|Purpose|
|--- |--- |
|Basic Information|Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]).|
|Configuration|Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. You can send data as individual or serialized key-value pairs. For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized)] and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Elements of a cookie destination such as cookie name, domain, size, expiration interval, data format, etc.</li></ul>|
|Segment Mappings|Lets you: <br/><ul><li>Search for, add, and manage segments associated with all destination types. </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul>|

## Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] and cookie-based destinations transmit data synchronously, as a user takes action on a page.
* Server-to-server data transmission is asynchronous and can occur long after a user has left the page. The delivery type you select depends on your business requirements and how a particular data partner wants to, or can, receive data.

See [How to Choose a Destination Type](../../features/destinations/destinations.md#concept_88240D03005244DA91182932E9927003) for more information.

>[!MORE_LIKE_THIS]
>
>* [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination)

## Configure a Cookie Destination {#create-cookie-destination}

A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

## Basic Information {#section_2CA42BC9306E41D6B2CD310C35CB8F65}

This section contains fields and options that start the cookie destination creation process. To complete this section:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. Name the destination. Avoid abbreviations and special characters.
1. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
1. *(Optional)* In the **[!UICONTROL Platform]** list, leave the default set to **[!UICONTROL All]**. Currently, these options don't do anything. They're designed to support features that may be added at a later date.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
1. *(Optional)* Select an **[!UICONTROL Auto-fill Destination Mapping]**. Options include:
    * **[!UICONTROL Segment ID]**: Automatically adds and sends the segment ID to the destination.
    * **[!UICONTROL Integration Code Value]**: Automatically adds and sends the segment integration code to the destination mapping. The integration code is a unique identifier created and used by the customer. It is limited to 255 characters, maximum.
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

## Data Export Labels {#section_DBA5FEE725E142AEA979BECBA7FE9DD5}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Click **[!UICONTROL Save]**.

## Configuration {#configuration}

This section contains fields and options that let you set up the cookie for your destination.

>[!NOTE]
>
>[!DNL Audience Manager] encodes data written to the destination cookie. For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`. To complete this section:

1. Click **[!UICONTROL Configuration]** to expose the controls
1. Name the cookie. Avoid abbreviations and special characters.
1. Choose a data format option. These options let you choose the delimiters and separators for the key-value pairs that send segment data to a destination. Format options include:
    * **Single key:** Lets you set the key in a key-value pair. You'll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
    * **Multi key:** Lets you set the key and value for a key-value pair. You'll create the key-value pair after you select a segment in the Segment Mappings section below.
   See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Click **[!UICONTROL Save]**.

All other settings are optional. For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](../../features/destinations/manage-destinations.md#optional-settings-cookies).

## Segment Mappings {#segments-mapping}

This section lets you search for and add segments to your destination. To complete this section:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** to browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In the [!UICONTROL Edit Mapping] dialog:
    * **[!UICONTROL Mapping]** lets you set a value for the key specified in the Configuration section above.
    * **[!UICONTROL Publish from]** lets you set start and end date for the destination. If the end date is blank, the destination never expires.
1. Click **[!UICONTROL Save]**.
1. Click **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

A [!DNL URL] destination makes pixel calls from a page to your destination. Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

## Basic Information {#basic-info}

This section contains fields and options that start the URL destination creation process. To complete this section:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. Name the destination. Avoid abbreviations and special characters.
1. *(Optional)* Describe the destination. A concise description is an effective way to define or provide more information about a destination.
1. *(Optional)* In the **[!UICONTROL Platform]** list, leave the default set to **[!UICONTROL All]**. Currently, these options don't do anything. They're designed to support features that may be added at a later date.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
1. *(Optional)* Select an **[!UICONTROL Auto-fill Destination Mapping]**. Options include:
    * **[!UICONTROL Segment ID]**: Automatically adds and sends the segment ID to the destination.
    * **[!UICONTROL Integration Code Value]**: Automatically adds and sends the segment integration code to the destination mapping. The integration code is a unique identifier created and used by the customer. It is limited to 255 characters, maximum.
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

## Data Export Labels {#data-export-labels}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Click **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. This section is optional. To complete this section:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(Optional)* Select the **[!UICONTROL Serialize]** check box.
   This lets you send segments to a destination sequentially rather than making separate calls for each segment. Serialization helps make data transfers efficient. Selecting this check box exposes the URL and delimiter fields. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| Field | Description |
|--- |--- |
|Base URL|The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%` [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Example: `https://www.myCompany.com/%alias%...`|
|Secure URL|The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Example: `https://www.myCompany.com/%alias%...`|
|Delimiter|The symbol that separates the segment variables in the [!DNL URL] string. This is usually a comma or semi-colon. Get this information from your destination partner.|

## Segment Mappings {#segment-mappings}

This section lets you search for and add segments to your destination. To complete this section:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In [!UICONTROL Edit Mapping]:
    * **[!UICONTROL Mappings]**: Provide the key-value pairs used by the segment. 
    * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**: Choose a start and end date for the destination. If the end date is blank, the destination never expires.
1. Click **[!UICONTROL Done]**.

## Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] work independently of each other and are optional. You can create a cookie destination without using either of them.

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie Domain </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Syntax</b> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Cookie Domain</span> field accepts a simple text string that lets you set cookies on a specified domain or all domains. When using this feature: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Set only one domain for each cookie destination. Do not type multiple domains in the <span class="wintitle"> Cookie Domain</span> field. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Do not use wildcard characters. </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. This is the default setting. </p> <p>To set cookies on a specific domain and sub-domains: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Type the name of the domain in the <span class="wintitle"> Cookie Domain</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Start the domain name with a period. For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Example</b> </p> </td> 
   <td colname="col2"> <p>As a simple example, let's say we have a fictitious site called sports.com. Sports.com has domains for golf, baseball, and football. To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. See below for a more complex set of examples. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Complex Cookie Domain Examples

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Website </th> 
   <th colname="col2" class="entry">Cookie Domain: .sports.com <p>Cookie Set </p> </th> 
   <th colname="col3" class="entry">Cookie Domain: .golf.sports.com <p>Cookie Set </p> </th> 
   <th colname="col4" class="entry">Cookie Domain: Blank <p>Cookie Set </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Yes </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Yes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Yes </td> 
   <td colname="col3"> Yes </td> 
   <td colname="col4"> Yes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Yes </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Yes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Yes </td> 
  </tr> 
 </tbody> 
</table>

## Publish Data To {#publish-data-to}

The [!UICONTROL Publish Data To] settings return a cookie if the domain meets the criteria set by the options you select. Options include:

* **[!UICONTROL All of our domains]**: (Default) Returns a [!DNL cookie] for any domain.
* **[!UICONTROL Only the selected domains]**: Returns a cookie only for the domains selected in the domains list.
* **[!UICONTROL All of our domains except the selected domains]**: Prevents selected domains from receiving a [!DNL cookie]. All other domains can receive a [!DNL cookie].

>[!MORE_LIKE_THIS]
>
>* [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination)

## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. Go to **[!UICONTROL Audience Data > Destinations]** and find the [!DNL S2S] destination you want to work with.
1. In the [!UICONTROL Action] column, click the pencil icon to edit the destination.
   * In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * In [!UICONTROL Edit Mapping]:
        * **[!UICONTROL Mappings]**: Set a value for the [key-value pair](../../features/destinations/key-value-pairs.md) used by this destination.
        * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**: Choose a start and end date for the destination. If the end date is blank, the destination never expires.
1. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] work with the [!DNL Export Controls] you set on a data source. [!DNL Data Export Labels] prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

To add export labels to a destination:

1. Click **[!UICONTROL Audience Data]**:
    * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
    * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. Select a [!DNL Data Export Label]. Leave the check boxes blank if you don't want to set any export restrictions. Export labels include the following options:
    * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
    * **[!UICONTROL This destination may be used for on-site ad targeting]**
    * **[!UICONTROL This destination may be used for for off-site ad targeting]**
    * **[!UICONTROL This destination may be used for for on-site ad personalization**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. Click **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [Create a Data Source](../../features/manage-datasources.md#create-data-source)
