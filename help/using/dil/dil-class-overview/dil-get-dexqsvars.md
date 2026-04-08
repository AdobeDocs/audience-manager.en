---
description: Retrieves a specific value from an ad server.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
TQID: https://experienceleague.adobe.com/O8xeJARK4qVGj8SOXmO8OHLqfOcSPZZWvWoGad0Wji8
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
# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>Beginning in July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the [!DNL DIL] extension.
>
>Existing customers can continue using their [!DNL DIL] implementation. However, Adobe will not be developing [!DNL DIL] beyond this point. Customers are encouraged to evaluate [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) for their long term data collection strategy.
>
>Customers looking to implement new data collection integrations after July 2023 should use [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

Retrieves a specific value from an ad server.

 **Function Signature:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parameters** 

|  Name  | Type  | Description  |
|---|---|---|
|  `variableName`  | String  | The name of the variable you want to get a value for.  |
|  `partner`  | String  | The partner name to search for.  |
|  `containerNSID`  | Integer  | The [!DNL NSID] of the container you're searching for. Defaults is `0`.  |

**Response**

Returns the variable value for a [!UICONTROL DIL] instance.

**Sample Code** 

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
