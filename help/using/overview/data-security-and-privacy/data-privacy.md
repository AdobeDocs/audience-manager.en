---
description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy
solution: Audience Manager
title: Data Privacy
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
---

# Data Privacy{#data-privacy}

Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

## Data Privacy {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager recognizes the implicit pact between consumers and the online brands with which they interact. Both parties benefit from the transparent exchange of anonymous data elements:

* Consumers receive personalized content, discounted product offers, and streamlined user experiences. 
* Brands receive vital revenue streams supporting multiple online business models.

In our continuing support of this model, Audience Manager remains committed to providing transparency and control to consumers, and meeting or exceeding the Online Behavioral Advertising (OBA) Self-Regulatory Principles.

## Opt-Out Management {#opt-out-management}

The opt-out documentation has been extended and moved to a separate part of our documentation. See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**IP Obfuscation Methodology:** Following the principles of "Privacy By Design", Adobe Audience Manager allows customers to enable [!DNL IP] obfuscation from the UI, either globally across all geographic regions or for specific countries. When you enable this setting, the last octet (the last portion) of the [!DNL IP] address is immediately discarded when the [!DNL IP] address is ingested into Audience Manager. Audience Manager discards this part of the [!DNL IP] address prior to processing (including before any optional geographic lookup or logging of the [!DNL IP] address). For example:

* Before: `255.255.255.255`
* After: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable [!DNL IP] address obfuscation in the Audience Manager UI.

Watch the video below to understand how [!DNL IP] address obfuscation works in Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geographic Segmentation:** If you enable [!DNL IP] address obfuscation, the remaining octets of the [!DNL IP] address can still be used for geo-segmentation and reporting in Audience Manager. If you do not enable [!DNL IP] address obfuscation, Audience Manager uses the full [!DNL IP] address. You can use the Geographic Segmentation feature that allows you to identify an [!DNL IP] location by geographic area in either case, but with some slight loss of precision when [!DNL IP] obfuscation is being used. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. Obtaining region and country-level information should only be slightly impacted. Geographic Segmentation data is granular only to the city level or postal code level, and not to the individual level. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Related concepts {#related-concepts}

* [Opt-out Management](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Privacy and Data Retention FAQ](/help/using/faq/faq-privacy.md)