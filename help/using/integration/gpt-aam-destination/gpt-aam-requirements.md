---
description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
---
# Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL Google Ad Manager] (formerly DFP) either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **Add [!UICONTROL DIL]:** Deploy [!UICONTROL Data Integration Library (DIL)] code on all the pages you want to target. [!UICONTROL DIL] writes Audience Manager segment data and user IDs to cookies that get used by [!DNL GPT] for targeting.

* **Create a [!UICONTROL Cookie Destination]:** [!DNL GPT] must be set up as a cookie-based destination in Audience Manager.

* **Implement Cookie Checking Code:** Wrap the [!DNL GPT] `.setTargeting` API method in our recommended [cookie checking code](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **Add the `AamGpt` Function:** The `AamGpt` code captures data from Audience Manager cookies and sends it to [!DNL GPT]. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

  >[!NOTE]
  >
  >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **Send Delivery Logs to Audience Manager:** If you want a segment delivery report (optional), provide Audience Manager with a daily log that contains impression-level delivery data. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Only Qualified Segments are Sent to GPT

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. For example, say you set up 100 Audience Manager segments. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL Google Ad Manager], using [!DNL GPT]. You'll need to provide your [!DNL Google Ad Manager] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. Please contact your Audience Manager consultant or Customer Care to discuss migration.

>[!MORELIKETHIS]
>
>* [GPT API Reference Guide](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
