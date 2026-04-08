---
description: Used to let DIL know that it is loaded after the window loads.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
TQID: https://experienceleague.adobe.com/gLycCnA5nwb-91miUts-VvlFK4YfVxvju7GAl-NZW8w
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
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
# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>Beginning in July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the [!DNL DIL] extension.
>
>Existing customers can continue using their [!DNL DIL] implementation. However, Adobe will not be developing [!DNL DIL] beyond this point. Customers are encouraged to evaluate [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) for their long term data collection strategy.
>
>Customers looking to implement new data collection integrations after July 2023 should use [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

Used to let DIL know that it is loaded after the window loads.

 **Function Signature:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Sample Code

```
DIL.isAddedPostWindowLoad();
```
