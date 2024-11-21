---
title: Update your data collection library for Audience Manager from the AppMeasurement JavaScript library to the Web SDK JavaScript library.
description: Understand the steps to update your data collection library for Audience Manager from the AppMeasurement JavaScript library to the Web SDK JavaScript library.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
---
# Update your data collection library for Audience Manager from the AppMeasurement JavaScript library to the Web SDK JavaScript library

## Intended audience {#intended-audience}

This page is for Audience Manager and Adobe Analytics customers who use the [!DNL AppMeasurement] JavaScript library to send web data to Audience Manager.

Refer to the table below for guidance on migration steps to Web SDK, depending on your current data collection method.

|Your existing data collection method | Web SDK migration instructions |
|---------|----------|
| [!DNL AppMeasurement] JavaScript library | Follow the instructions in this guide. |
| [!DNL Audience Manager] [tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Follow the instructions in [updating your data collection library from the Audience Manager tag extension to the Web SDK tag extension](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] JavaScript library + [!DNL Audience Manager] [DIL library](../dil/dil-overview.md) | Follow the instructions in [updating your data collection library from the Audience Manager tag extension to the Web SDK tag extension](dil-extension-to-web-sdk.md). |

## Migration overview {#overview}

Migrating from [!DNL AppMeasurement] to [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) is primarily an Adobe Analytics migration. For Audience Manager customers, this migration also includes Audience Manager. Both must be migrated together. If you mainly work with Audience Manager, ensure you involve the Analytics team in this migration.

If you use [!DNL AppMeasurement] for Audience Manager data collection, you are currently using the [!DNL Server-side Forwarding (SSF)] approach to send Analytics data to Audience Manager. In this setup, the Analytics data collection request is forwarded to Audience Manager, which also handles the Audience Manager response to the page.

This has been the standard approach for many years and is likely your current setup. If your [!DNL AppMeasurement] library contains the `AudienceManagement` module and your data collection calls include the `/10/` path in the request (`/b/ss/examplereportsuite/10/`), then this guide is for you.
 

## Server-side Forwarding (SSF) versus Web SDK data flows {#data-flows}

Understanding the data flow differences between Analytics and Audience Manager when moving to Web SDK (and the Edge Network) is crucial for the instructions below. 

With server-side forwarding, the Analytics regional data collection node collects the data, transforms it into a signal accepted by Audience Manager, sends it to Audience Manager, and returns the Audience Manager response to the page. The [!DNL AudienceManagement] module in the [!DNL AppMeasurement] library then handles the response (e.g., dropping cookies, sending URL destinations). This process is called server-side forwarding because Analytics forwards the data to Audience Manager using Adobe servers.

With Web SDK, the Edge Network sends data to Analytics and Audience Manager in separate actions. The Web SDK is a single library that sends data to all solutions, and the Edge Network transforms solution-agnostic data points into solution-specific formats.

In this new data flow, all data is sent to an Edge Network [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview), which you can [configure](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) to send data to Adobe solutions as needed. For Audience Manager, enabling the Audience Manager service on the datastream transforms [!DNL XDM] and Analytics data into signals accepted by Audience Manager. The Edge Network also returns the Audience Manager response to the page, where the Web SDK handles the response, similar to how [!DNL AppMeasurement] and the [!DNL AudienceManagement] module did.

## Tags versus non-Tags migration {#tags-vs-non-tags}

Whether you are using Tags with the [!DNL AppMeasurement] extension, the [!DNL AppMeasurement] library in another tag management system, or placing [!DNL AppMeasurement] directly on the page, the steps for migrating Audience Manager to the Web SDK are the same. Since the Audience Manager migration depends on the Analytics migration, the steps to migrate from [!DNL AppMeasurement] to Web SDK are determined during the Analytics migration.

That information is covered in the Analytics documentation for [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) or [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)-based implementations.

## Advantages and disadvantages of this implementation path

Using this migration approach has both advantages and disadvantages. Carefully weigh each option to decide which approach is best for your organization.

| Advantages | Disadvantages |
| --- | --- |
| <ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic.</li><li>**Does not require a schema**: For this stage of migrating to the Web SDK, you don't need an XDM schema. Instead, you can populate the `data` object, which sends data straight to Audience Manager. Once migration to the Web SDK is complete, then you can create a schema for your organization and use datastream mapping to populate applicable XDM fields. If a schema were required at this stage of the migration process, your organization would be forced to use an Audience Manager XDM schema. Use of this schema makes it more difficult for your organization to use your own schema in the future.</li></ul> | <ul><li>**Implementation technical debt**: Since this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed.</li><li>**Requires mapping to send data to Platform**: When your organization is ready to use Real-Time CDP, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the `data` object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li></ul> |

Adobe recommends following this implementation path in the following scenarios:

* You have an existing implementation using the Adobe Analytics AppMeasurement JavaScript library. If you have an implementation using the Audience Manager tag extension, follow [Migrate from the Audience Manager tag extension to the Web SDK tag extension](dil-extension-to-web-sdk.md) instead.
* You intend to use Real-Time CDP in the future, but do not want to replace your Audience Manager implementation with a Web SDK implementation from scratch. Replacing your implementation from scratch on the Web SDK requires the most effort, but also offers the most viable long-term implementation architecture. If your organization is willing to go through the effort of a clean Web SDK implementation, see the [Web SDK documentation](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) for more details.

## Steps required to migrate to the Web SDK

Follow the steps below to migrate your data collection integration to Web SDK.

+++**1. Migrate your Analytics implementation**.

Work with your Analytics team to follow the steps for Analytics migration in either the [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) or [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)-based implementations. After you have migrated your Analytics implementation, continue to the following step.

+++

+++**2. Create and configure a datastream**

Create a datastream in Adobe Experience Platform Data Collection. When you send data to this datastream, it forwards data to Audience Manager. In the future, this same datastream forwards data to Real-Time CDP.

1. Navigate to [experience.adobe.com](https://experience.adobe.com) and log in using your credentials.
1. Use the home page or product selector in the top right to navigate to **[!UICONTROL Data Collection]**.
1. In the left navigation, select **[!UICONTROL Datastreams]**.
1. Select the datastream that you created as part of your Analytics migration in step 1.
1. Select **[!UICONTROL Add Service]**.
1. In the service drop-down menu, select **[!UICONTROL Audience Manager]**.
1. Check the **[!UICONTROL Cookie Destinations Enabled]** and **[!UICONTROL URL Destinations Enabled]** options. These options allow the Edge Network to return those Audience Manager destination types to the page. 
1. Make sure the **[!UICONTROL Enable XDM Flattened Fields]** is disabled. This option disables the automatic transformation of Analytics variables into Audience Manager signals. This option is designed to maintain backward compatibility for users who migrated to Web SDK before the Edge Network automatically transformed the Analytics data to Audience Manager signals.

    >[!NOTE]
    >
    >Migrating to Web SDK with the **[!UICONTROL Enabled XDM Flattened Fields]** option enabled requires that any data needed in Audience Manager formatted as XDM and all Audience Manager traits using props, eVars, or events be updated to look for XDM-formatted data instead. Adobe recommends leaving this option disabled. 


    ![Add Audience Manager service](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Select **[!UICONTROL Save]** to save the datastream configuration.

Your datastream is now ready to receive and pass along data to Audience Manager. Note the datastream ID, as this ID is required when configuring the Web SDK in code.

+++

+++**3. Enable Third-Party ID Syncs and set the Audience Manager Container ID**

1. Navigate to [experience.adobe.com](https://experience.adobe.com) and log in using your credentials.
1. Use the home page or product selector in the top right to navigate to **[!UICONTROL Data Collection]**.
1. In the left navigation, select **[!UICONTROL Datastreams]**.
1. Select the datastream that you created as part of your Analytics migration in step 1.
1. Select **[!UICONTROL Edit]** in the upper right corner of the datastream configuration page.
1. Expand the **[!UICONTROL Advanced Options]** drop down menu and enable the **[!UICONTROL Third Party ID Sync]** functionality if it is not already enabled. This option tells the Edge Network to return Partner ID Syncs for Audience Manager and Experience Platform data partners.    

    ![Enable third party ID sync.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. In most cases, you can leave the **[!UICONTROL Third Party ID Sync Container ID]** field blank. It will it will default to `0`. However, if you prefer to ensure the right container ID is used, follow the next steps:
    * Open a browser window in incognito or private mode and navigate to a page that is part of the migration.
    * Use the developer tools of the browser to filter for the network call to `dpm.demdex.net/id`. This call will only fire on the first page of a first visit, which is why an incognito or private browser is needed.
    * View the payload of the request. If the `d_nsid` parameter is different than zero, copy it to the **[!UICONTROL Third Party ID Sync Container ID]** field.

1. Select **[!UICONTROL Save]**.

Your datastream is now ready to both send data to Audience Manager and pass the Audience Manager responses to the Web SDK.

+++

+++**4. Install the Web SDK JavaScript library**

See [Install the Web SDK using the JavaScript library](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) for details and code blocks to use. Reference the latest version of `alloy.js` so its method calls can be used.

+++

+++**5. Configure the Web SDK**

Set up your implementation to point to the datastream created in step 1 by using the Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) command. The `configure` command must be set on every page, so you can include it alongside the library installation code.

Use the [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) and [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) properties within the Web SDK `configure` command:

* Set the `edgeConfigId` to the datastream ID retrieved from the previous step.
* Set the `orgId` to your organization's IMS org ID.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

You can optionally set other properties in the [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) command depending on your organization's implementation requirements.

+++

+++**6. Update code logic to use a JSON payload**

Change your Audience Manager implementation so that it does not rely on `AppMeasurement.js` or the `s` object. Instead, set variables into a correctly formatted JavaScript object, which is converted to a JSON object when sent to Adobe. Having a [data layer](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) on your site helps tremendously when setting values, as you can continue referencing those same values.

To send data to Audience Manager, the Web SDK payload must use `data.__adobe.audiencemanager` with all analytics variables set within this object. Variables within this object share identical names and formats as their AppMeasurement variable counterparts. For example, if you set the `products` variable, do not split it into individual objects like you would with XDM. Instead, include it as a string exactly is if you set the `s.products` variable:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Ultimately, this payload contains all desired values, and all references to the `s` object in your implementation are removed. You can use any of the resources that JavaScript provides to set this payload object, including dot notation to set individual values.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**7. Update method calls to use the Web SDK**

Update all instances where you call [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) and [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), replacing them with the [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) command. There are three scenarios to consider:

* **Page view tracking**: Replace the page view tracking call with the Web SDK `sendEvent` command:

  ```js
  // If your current implementation has this line of code:
  s.t();

  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Automatic link tracking**: The [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) configuration property is enabled by default. It automatically sets the correct link tracking variables to send data to Audience Manager. If you want to disable automatic link tracking, set this property to `false` within the [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) command.

* **Manual link tracking**: The Web SDK does not have separate commands between pageview and non-pageview calls. Provide that distinction within the payload object.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");

  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**8. Validate and publish changes**

Once you have removed all references to AppMeasurement and the `s` object, publish your changes to your development environment to validate that the new implementation works. Once you have validated that everything works correctly, you can publish your updates to production.

If migrated correctly, `AppMeasurement.js` is no longer required on your site, and all references to this script can be removed.

+++

At this point, your Audience Manager implementation is fully migrated to the Web SDK and is prepared to move to Real-Time CDP in the future.

## The `data.__adobe.audiencemanager` node {#data-note}

The `data.__adobe.audiencemanager` node is used for Audience Manager implementations that do not rely on Analytics. It stores custom Audience Manager key/value pairs that were previously sent via the [DIL library](../dil/dil-overview.md) library, as described in the [tag extension migration guide](dil-extension-to-web-sdk.md).

While the `data.__adobe.audiencemanager` node is not needed for the migration outlined in this guide, the new data flow explained here allows data to be sent to Audience Manager without being recorded in Analytics.

If you need to send a custom key/value pair to Audience Manager without including it in Analytics, you can use the `data.__adobe.audiencemanager` node. Any data set in this node will be appended to the Audience Manager-transformed Analytics data in the data collection server call.

