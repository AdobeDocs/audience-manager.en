---
description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy
solution: Audience Manager
title: Data Privacy
uuid: 1d26af5e-3b83-4432-8c89-80359b437517
index: y
internal: n
snippet: y
translate: y
---

# Data Privacy

Contents: 

* [ Data Privacy](../../c_am_overview_intro/c_data_security_and_privacy/data_privacy.md#section_3C0E97906232432296F2B2200B0BFA4F)
* [ Consumer Privacy Protection](../../c_am_overview_intro/c_data_security_and_privacy/data_privacy.md#section_8269FC81B9514F62925BA63DFB9BCC1D)
* [ Opt-Out Management](../../c_am_overview_intro/c_data_security_and_privacy/data_privacy.md#section_FAEB5029359A4AA8A466E3185B9EA04F)
* [ Collecting IP Addresses](../../c_am_overview_intro/c_data_security_and_privacy/data_privacy.md#section_6E615E8AAE0A4C39A3716115C270569C)

## Data Privacy {#section_3C0E97906232432296F2B2200B0BFA4F}

See the [ Adobe Privacy Center](http://www.adobe.com/privacy/opt-out.html). 

## Consumer Privacy Protection {#section_8269FC81B9514F62925BA63DFB9BCC1D}

Audience Manager recognizes the implicit pact between consumers and the online brands with which they interact. Both parties benefit from the transparent exchange of anonymous data elements: 


* Consumers receive personalized content, discounted product offers, and streamlined user experiences.
* Brands receive vital revenue streams supporting multiple online business models.


In our continuing support of this model, Audience Manager remains committed to providing transparency and control to consumers, and meeting or exceeding the Online Behavioral Advertising (OBA) Self-Regulatory Principles. 

## Opt-Out Management {#section_FAEB5029359A4AA8A466E3185B9EA04F}

The opt-out documentation has been extended and moved to a separate part of our documentation. See [ Opt-out Management](../../c_am_overview_intro/c_data_security_and_privacy/opt-out-management.md#concept_1EC49431ED7D4012BD930ECF8A6D732F). 

<!-- <p>  </p>
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
    <td colname="col2"> <p>The <a href="http://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="http://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../c_features/c_declared_id/declared_id_about.md#concept_CB958007B9DA4251BA724B5607AD9FC3" format="dita" scope="local"> Declared ID Targeting</a>. </p> </td> 
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
</table> -->

## Collecting IP Addresses {#section_6E615E8AAE0A4C39A3716115C270569C}

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws. 

The IP address of a visitor to a customer’s website is transmitted to an Adobe Data Processing Center (DPC) where the IP address may be stored. Depending on the network configuration for the visitor, the IP address does not necessarily represent the IP address of the visitor’s computer. For example, the IP address could be the external IP address of a Network Address Translation (NAT) firewall, HTTP proxy, or Internet gateway. 

**Replacing the Last Octet of the IP Address: **Adobe has developed a new “privacy by design” setting that can be enabled by Audience Manager Consulting. When this setting is enabled, the last octet (the last portion) of the IP address is immediately hidden when the IP address is collected by Adobe. Audience Manager masks this part of the IP address prior to processing (including before any optional geo-lookup of the IP address). For example: 


* Before: ` 123.45.67.89`
* After: ` 123.45.67.0`


When this feature is enabled, the IP address is altered so that it may no longer be considered identifiable as personal information or personal data in some jurisdictions. As a result, you may be able to use the obfuscated IP address in Audience Manager in compliance with data privacy laws in certain countries that do not permit the collection of personal information or have limits on the use of personal data. Please consult with your counsel to determine if this is applicable to the jurisdiction(s) where you will use Audience Manager and your use case(s). Obtaining city-level information will likely be significantly impacted by the obfuscation of the IP address. Obtaining region- and country-level information should only be slightly impacted. 


>[!NOTE]
>
>Contact your Audience Manager Consulting representative to enable the IP obfuscation feature.



**Geographic Segmentation: **If customers enable the replacement of the last octet of the IP address, the remaining values of the IP address can still be utilized for geo-segmentation and reporting in Audience Manager. If the last octet of the IP address has not been obfuscated, the full IP address is used. Customers can use the Geographic Segmentation feature that allows the customer to map out visitor location by geographic area in either case, but with some slight loss of precision when IP obfuscation is being used. Geographic Segmentation data is granular only to the city level or zip code level, and not to the individual level. 


