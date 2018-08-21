---
description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Launch), DIL, Akamai, and the control database.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management Components
uuid: 3373a1fb-9777-4414-9500-faa1e610a4b1
index: y
internal: n
snippet: y
translate: y
---

# Tag Management Components

Audience Manager contains the following components: 

* [ Client Portal ](../../c_reference/c_compintro/c_comptag.md#section_FCB110B4DEB549FAA84CB65A266EB673)
* [ DIL/TIM Container ](../../c_reference/c_compintro/c_comptag.md#section_94E9A847D45D40939922A64C6560DFA4)
* [ Data Information Library (DIL) ](../../c_reference/c_compintro/c_comptag.md#section_5CF17DB718624223993CF1B5417B7632)
* [ Akamai ](../../c_reference/c_compintro/c_comptag.md#section_10236EBD13C44011BF386B7404A7205D)
* [ Control Database ](../../c_reference/c_compintro/c_comptag.md#section_1B0E00C342F34EA895677DFBB48298F8)

## Client Portal {#section_FCB110B4DEB549FAA84CB65A266EB673}

The client portal is the primary user interface (UI) for tag and data management. Customers use the portal to work with tags, build traits and segments, set up destinations, and monitor campaign performance with reports. 

## DIL/TIM Container {#section_94E9A847D45D40939922A64C6560DFA4}

The DIL container helps deploy Audience Manager data collection code to your website. TIM is the deprecated [ Tag Insertion Manager](../../c_features/c_tim1_about.md#concept_B824B70BF53D4F17A0CD938FF1FCF2C5). It is no longer used by [!DNL  Audience Manager]. Instead, you use [ Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the Audience Manager extension in [ Adobe Launch](https://docs.adobelaunch.com/extension-reference/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. The DTM container works with the Data Information Library (DIL) to collect data from your site and send it to Audience Manager. 

## Data Integration Library (DIL) {#section_5CF17DB718624223993CF1B5417B7632}

The [ Data Information Library](../../c_api/c_dil/c_dil.md#concept_6D73ED3DBA604EE49B66B5572AA6A32C) (DIL) is a self-contained API module that collects data from your website. DIL helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data. DIL performs these actions automatically. Additionally, DIL is compact. It is a self-contained code library that helps reduce the amount of code required to collect information. Finally, DIL helps you integrate Audience Manager with other products in the Adobe Experience Cloud. 

## Akamai {#section_10236EBD13C44011BF386B7404A7205D}

Audience Manager uses [ Akamai](http://www.akamai.com/html/about/index.html) to host and deliver container code from our own tag management platform known as TIM (Tag Insertion Manager). However, code deployment with TIM has been phased out in favor of Adobe Dynamic Tag Management and Adobe Launch. 

## Control Database {#section_1B0E00C342F34EA895677DFBB48298F8}

The control database: 


* Processes client input from the portal (for example, creating traits and destinations).
* Transmits data to Akamai, which includes data used to build the container template and destination publishing iFrame.
* Returns data for UI reporting systems.

