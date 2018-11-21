---
description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Launch), DIL, Akamai, and the control database.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management Components
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
index: y
internal: n
snippet: y
---

# Tag Management Components{#tag-management-components}

Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Launch), DIL, Akamai, and the control database.

<!-- 

c_comptag.xml

 -->

Audience Manager contains the following components:

* [Client Portal](../../reference/system-components/components-tag-management.md#section_FCB110B4DEB549FAA84CB65A266EB673) 
* [DIL/TIM Container](../../reference/system-components/components-tag-management.md#section_94E9A847D45D40939922A64C6560DFA4) 
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#section_5CF17DB718624223993CF1B5417B7632) 
* [Akamai](../../reference/system-components/components-tag-management.md#section_10236EBD13C44011BF386B7404A7205D) 
* [Control Database](../../reference/system-components/components-tag-management.md#section_1B0E00C342F34EA895677DFBB48298F8)

## Client Portal {#section_FCB110B4DEB549FAA84CB65A266EB673}

The client portal is the primary user interface (UI) for tag and data management. Customers use the portal to work with tags, build traits and segments, set up destinations, and monitor campaign performance with reports.

## DIL/TIM Container {#section_94E9A847D45D40939922A64C6560DFA4}

The [!UICONTROL DIL] container helps deploy [!DNL Audience Manager] data collection code to your website. [!UICONTROL TIM] is the deprecated Tag Insertion Manager. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. The [!UICONTROL DTM] container works with the [!UICONTROL Data Information Library (DIL)] to collect data from your site and send it to [!DNL Audience Manager].

## Data Integration Library (DIL) {#section_5CF17DB718624223993CF1B5417B7632}

The [Data Information Library](../../c-dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data. [!UICONTROL DIL] performs these actions automatically. Additionally, [!UICONTROL DIL] is compact. It is a self-contained code library that helps reduce the amount of code required to collect information. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#section_10236EBD13C44011BF386B7404A7205D}

[!DNL Audience Manager] uses [Akamai](https://www.akamai.com/html/about/index.html) to host and deliver container code from our own tag management platform known as [!UICONTROL TIM (Tag Insertion Manager)]. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#section_1B0E00C342F34EA895677DFBB48298F8}

The control database:

* Processes client input from the portal (for example, creating traits and destinations). 
* Transmits data to Akamai, which includes data used to build the container template and destination publishing iFrame. 
* Returns data for UI reporting systems.

