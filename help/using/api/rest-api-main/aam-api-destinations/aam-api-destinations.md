---
description: Methods that let you work programmatically with destination features.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Destination API Methods
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
---

# Destination [!UICONTROL API] Methods {#destination-api-methods}

Methods that let you work programmatically with destination features.

<!--
c_destinations_api.xml
-->

In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) that you want to share data with.

## Destination Types: [!UICONTROL URL] and [!UICONTROL Cookie] {#reference_279437B2EC9143B6B653874C80A79B54}

Lists the variables used by the `destinationType` parameter. Specify `push` or `ADS` to work with a [!UICONTROL URL] or [!UICONTROL cookie destination]. You cannot create [!UICONTROL server-to-server destinations] with the available destination [!UICONTROL API] methods.

<!--
r_destination_types.xml
-->

|  API Destination Type  | UI Destination Type  |
|---|---|
|  `PUSH`  | [!UICONTROL URL]  |
|  `ADS`  | [!UICONTROL Cookie]  |

>[!MORE_LIKE_THIS]
>
>* [How to Choose a Destination Type](../../../features/destinations/destinations.md#concept_88240D03005244DA91182932E9927003)
