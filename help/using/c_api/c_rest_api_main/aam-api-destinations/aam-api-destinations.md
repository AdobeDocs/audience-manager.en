---
description: Methods that let you work programmatically with destination features.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Destination API Methods
uuid: d5d22eef-b51e-434b-9472-9d9eb40363e4
index: y
internal: n
snippet: y
translate: y
---

# Destination API Methods

Methods that let you work programmatically with destination features.

## <wintitle> Destination API </wintitle> Methods {#concept_5BDA346C376C4B719EA394108AB2735A}

Methods that let you work programmatically with destination features. 
<draft-comment otherprops="merge">
  c_destinations_api.xml 
</draft-comment>



In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) that you want to share data with. 

## Destination Types: <wintitle> URL </wintitle> and <keyword> Cookie </keyword> {#reference_279437B2EC9143B6B653874C80A79B54}

Lists the variables used by the 
<codeph>
  destinationType
</codeph> parameter. Specify 
<codeph>
  push
</codeph> or 
<codeph>
  ADS
</codeph> to work with a 
<wintitle>
  URL
</wintitle> or 
<wintitle>
  cookie destination
</wintitle>. You cannot create 
<wintitle>
  server-to-server destinations
</wintitle> with the available destination 
<wintitle>
  API
</wintitle> methods. 
<draft-comment otherprops="merge">
  r_destination_types.xml 
</draft-comment>


>
>

>
>
>|  API Destination Type  | UI Destination Type  |
>|---|---|
>|  `PUSH`  | [!UICONTROL URL]  |
>|  `ADS`  | [!UICONTROL Cookie]  |

>[!MORE_LIKE_THIS]
>
>* [How to Choose a Destination Type](destinations.md#concept_88240D03005244DA91182932E9927003)
