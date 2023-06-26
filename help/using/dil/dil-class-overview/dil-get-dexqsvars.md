---
description: Retrieves a specific value from an ad server.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
---
# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>Starting with July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the DIL extension.
><br><br>Existing customers can continue using their DIL implementation, but customer support will be limited to security issues only.
><br><br>Customers looking to implement new data collection integrations should use the [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

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
