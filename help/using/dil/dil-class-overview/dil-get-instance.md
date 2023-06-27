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
---
# getDil{#getdil}

>[!WARNING]
>
>Starting with July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the DIL extension.
><br><br>Existing customers can continue using their DIL implementation, but no support will be provided after this date.
><br><br>Customers looking to implement new data collection integrations should use the [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

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
