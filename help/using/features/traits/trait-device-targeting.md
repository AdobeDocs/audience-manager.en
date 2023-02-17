---
description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Device Targeting With Platform-level Keys
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
---
# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Starting with February 2023, Google has updated the functionality of [!DNL Google Chrome] and all [!DNL Chromium]-based browsers to minimize the information collected via the `User-Agent` header.
>Starting with March 2023, Audience Manager supports these updates by leveraging [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). To continue using trait information provided via the `User-Agent` header, you must use [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) and enable [High Entropy User-Agent Client Hints](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>These updates are not supported by [DIL](../../../using/dil/dil-overview.md), so Audience Manager customers who use [!DNL DIL] will not be able to collect trait information via the `User-Agent` header.

Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.

## Purpose of Platform-level Variables {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Platform-level Keys Defined by User Agent {#keys-user-agent}

The [!UICONTROL Data Collection Servers] extract the values for these keys from the [user agent header](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` requests. The values represent device-level information from the [!UICONTROL Device Atlas] database. The signals in the table below are available, as extracted from the user agent example. [Download a list of the most common keys](assets/device_keys.csv), according to [!UICONTROL Device Atlas] measurements.

|  [!DNL Signal]  | [!DNL Type]  | [!DNL Example]  |
|---|---|---|
|  `d_device_vendor`  | [!DNL VENDOR]  | [!DNL apple] |
|  `d_device_hardware_type`  | [!DNL HARDWARE]  | [!DNL mobile phone]  |
|  `d_device_os_version`  | [!DNL OS VERSION]  | [!DNL 5_0]  |
|  `d_device_os_name`  | [!DNL OS NAME]  | [!DNL ios]  |
|  `d_device_model`  | [!DNL MODEL]  | [!DNL iphone]  |
|  `d_device_marketing_name`  | [!DNL MARKETING NAME]  | [!DNL iphone]  |
|  `d_device_manufacturer`  | [!DNL MANUFACTURER]  | [!DNL apple]  |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md)
