---
description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Getting Started With Class-level DIL APIs
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
    internal-label: DIL implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
---
# Getting Started With Class-level DIL APIs{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Beginning in July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the [!DNL DIL] extension.
>
>Existing customers can continue using their [!DNL DIL] implementation. However, Adobe will not be developing [!DNL DIL] beyond this point. Customers are encouraged to evaluate [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) for their long term data collection strategy.
>
>Customers looking to implement new data collection integrations after July 2023 should use [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

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
