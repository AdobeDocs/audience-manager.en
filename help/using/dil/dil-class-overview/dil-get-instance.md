---
description: Retrieves a partner-specific DIL instance.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
TQID: https://experienceleague.adobe.com/C4wUrtnwE8WXsgDzXSTJQ1qUf-aB-RNWoBDbDFCNeZ8
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
# getDil{#getdil}

>[!WARNING]
>
>Beginning in July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the [!DNL DIL] extension.
>
>Existing customers can continue using their [!DNL DIL] implementation. However, Adobe will not be developing [!DNL DIL] beyond this point. Customers are encouraged to evaluate [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) for their long term data collection strategy.
>
>Customers looking to implement new data collection integrations after July 2023 should use [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

Retrieves a partner-specific DIL instance.

 **Function Signature:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameters

|  Name  | Type  | Description  |
|---|---|---|
|  `partner`  | String  | The partner name to search for.  |
|  `containerNSID`  | Integer  | Defaults is `0`. The NSID of the container you're searching for. Optional.  |

## Response

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Sample Code

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
