---
description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Getting Started With Class-level DIL APIs
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
---
# Getting Started With Class-level DIL APIs{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Starting with July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the DIL extension.
><br><br>Existing customers can continue using their DIL implementation, but no support will be provided after this date.
><br><br>Customers looking to implement new data collection integrations should use the [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

The class-level DIL APIs let you programmatically create and work with Audience Manager objects. The class-level APIs work with the other instance-level functions to set values or return data.

## Getting Started With Class-level DIL APIs {#get-started}

Describes authentication requirements and the text formatting used in the class-level [!UICONTROL DIL] documentation.

<!-- 

c_class_start.xml

 -->

When working with the class-level [!UICONTROL DIL] APIs:

* Access requires a partner name and container namespace ID (NSID). Contact your Audience Manager account manager to obtain this information. 
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you're working with. 
* [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.
