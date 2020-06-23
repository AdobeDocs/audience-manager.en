---
description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Understanding Calls to the Demdex Domain
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
---

# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] and the [!DNL Adobe Experience Platform Identity Service] make calls to and receive data from the `demdex.net` domain. This may seem like [!DNL Adobe] is working with an unusual third-party domain, but this is not the case. This section describes the elements in a `demdex.net` call.

|Call Element|Description|
|---|---|
|`demdex.net`|This is a legacy domain controlled by [!DNL Adobe]. It reflects the original, pre-acquisition name of [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] acquired [!DNL Demdex] in 2011 and re-branded the company as [!DNL Audience Manager]. It is difficult to change this domain because it is entwined deeply with [!DNL Audience Manager], the [!DNL Adobe Experience Cloud ID Service], and our installed user base. You may see other prefixes attached to legacy `demdex.net` calls (e.g., `dcs.demdex.net`, `fast.demdex.net`, etc.). Regardless of the prefix, a call to `something.demdex.net` is always a call to [!DNL Adobe] and not to some unknown or suspicious third-party domain.|
|`dpm`|[!DNL DPM] is an abbreviation for [!DNL Data Provider Match]. It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. This is the most common `demdex.net` call you'll see from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] call basics: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] call from [!DNL Audience Manager] sends data to the [!DNL Data Collection Servers] and [!DNL Profile Cache Servers]. See [Data Collection Components](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] call from the [!DNL Adobe Experience Cloud ID Service] is a request for a visitor ID. See [Cookies and the Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) and [How the Adobe Experience Platform Identity Service Requests and Sets IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html.</li></ul><br>Note: [!DNL Adobe Experience Cloud ID Service] customers can change the [!DNL DPM] prefix in the domain name. See [audienceManager Server and audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html).|

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)
