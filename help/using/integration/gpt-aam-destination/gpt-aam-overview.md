---
description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrate Google Ad Manager using Google Publisher Tags (GPT)
feature: Third Party Integrations
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
---
# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

The articles listed below provide an overview of how to integrate [!DNL Google Ad Manager] using Google Publisher Tags (GPT). You can use a server-side integration, or you can set up GPT as a destination to send Audience Manager segment data to [!DNL Google Ad Manager]. You will also learn the needed steps to ingest [!DNL Google Ad Manager] log files for reporting in Audience Manager.

* [Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  You can send qualified segments to [!DNL Google Ad Manager] either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.

* [Create a GPT Destination](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  You can send qualified segments to [!DNL Google Ad Manager] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.

* [Modify the GPT setTargeting API Call](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.

* [Audience Manager Code for Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt is a JavaScript function that reads Audience Manager cookie data and sends that information to Google Publisher Tags.
