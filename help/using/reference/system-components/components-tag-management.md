---
description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management Components
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
---
# Tag Management Components{#tag-management-components}

Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Dynamic Tag Manager and Adobe Experience Platform Launch), DIL, Akamai, and the control database.

<!-- 

c_comptag.xml

 -->

Audience Manager contains the following components:

* [Client Portal](../../reference/system-components/components-tag-management.md#client-portal) 
* [DIL/TIM Container](../../reference/system-components/components-tag-management.md#dil-tim) 
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#dil) 
* [Akamai](../../reference/system-components/components-tag-management.md#akamai) 
* [Control Database](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

The client portal is the primary user interface (UI) for tag and data management. Customers use the portal to work with tags, build traits and segments, set up destinations, and monitor campaign performance with reports.

## DIL/TIM Container {#dil-tim}

The [!UICONTROL DIL] container helps deploy [!DNL Audience Manager] data collection code to your website. [!UICONTROL TIM] is the deprecated Tag Insertion Manager. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) or the [!DNL Audience Manager] extension in [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) to configure and generate container code that you place on pages in your inventory. The [!UICONTROL DTM] container works with the [!UICONTROL Data Information Library (DIL)] to collect data from your site and send it to [!DNL Audience Manager].

## Data Integration Library (DIL) {#dil}

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] helps eliminate the need to write special code for data collection, integration, reading cookie values, and recovering page data. [!UICONTROL DIL] performs these actions automatically. Additionally, [!UICONTROL DIL] is compact. It is a self-contained code library that helps reduce the amount of code required to collect information. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] uses [Akamai](https://www.akamai.com/us/en/about/) to host and deliver container code from our own tag management platform known as [!UICONTROL TIM (Tag Insertion Manager)]. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!DNL Adobe Dynamic Tag Management] and [!DNL Adobe Experience Platform Launch].

## Control Database {#control-database}

The control database:

* Processes client input from the portal (for example, creating traits and destinations). 
* Transmits data to Akamai, which includes data used to build the container template and destination publishing iFrame. 
* Returns data for UI reporting systems.
