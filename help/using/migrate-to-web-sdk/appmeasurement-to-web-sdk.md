---
title: Update your data collection library for Audience Manager from the AppMeasurement JavaScript library to the Web SDK JavaScript library.
description: Understand the steps to update your data collection library for Audience Manager from the AppMeasurement JavaScript library to the Web SDK JavaScript library.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
---
# Update your data collection library for Audience Manager from the AppMeasurement JavaScript library to the Web SDK JavaScript library

## Intended audience {#intended-audience}

This page is intended for Audience Manager customers who are using AppMeasurement to bring web collection data into Audience Manager. For customers using the [Audience Manager tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), please read the guide on how to update your data collection library for Audience Manager [from the Audience Manager tag extension to the Web SDK tag extension](dil-extension-to-web-sdk.md).

## Advantages and disadvantages of this implementation path

Using this migration approach has both advantages and disadvantages. Carefully weigh each option to decide which approach is best for your organization.

| Advantages | Disadvantages |
| --- | --- |
| <ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic.</li><li>**Does not require a schema**: For this stage of migrating to the Web SDK, you don't need an XDM schema. Instead, you can populate the `data` object, which sends data straight to Audience Manager. Once migration to the Web SDK is complete, then you can create a schema for your organization and use datastream mapping to populate applicable XDM fields. If a schema were required at this stage of the migration process, your organization would be forced to use an Audience Manager XDM schema. Use of this schema makes it more difficult for your organization to use your own schema in the future.</li></ul> | <ul><li>**Implementation technical debt**: Since this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed.</li><li>**Requires mapping to send data to Platform**: When your organization is ready to use Real-Time CDP, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the `data` object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li></ul> |

Adobe recommends following this implementation path in the following scenarios:

* You have an existing implementation using the Adobe Analytics AppMeasurement JavaScript library. If you have an implementation using the Audience Manager tag extension, follow [Migrate from the Audience Manager tag extension to the Web SDK tag extension](dil-extension-to-web-sdk.md) instead.
* You intend to use Real-Time CDP in the future, but do not want to replace your Audience Manager implementation with a Web SDK implementation from scratch. Replacing your implementation from scratch on the Web SDK requires the most effort, but also offers the most viable long-term implementation architecture. If your organization is willing to go through the effort of a clean Web SDK implementation, see the [Web SDK documentation](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) for more details.

## Steps required to migrate to the Web SDK

The following steps contain concrete goals to work towards. Click each step for detailed instructions on how to accomplish it.

+++**1. Create and configure a datastream**

Create a datastream in Adobe Experience Platform Data Collection. When you send data to this datastream, it forwards data to Audience Manager. In the future, this same datastream forwards data to Real-Time CDP.

1. Navigate to [experience.adobe.com](https://experience.adobe.com) and log in using your credentials.
1. Use the home page or product selector in the top right to navigate to **[!UICONTROL Data Collection]**.
1. In the left navigation, select **[!UICONTROL Datastreams]**.
1. Select **[!UICONTROL New Datastream]**.
1. Enter the desired name, then select **[!UICONTROL Save]**.
1. Once the datastream is created, select **[!UICONTROL Add Service]**.
1. In the service drop-down menu, select **[!UICONTROL Audience Manager]**.

    ![Add Audience Manager service](assets/add-service.png) {style="border:1px solid lightslategray"}

Your datastream is now ready to receive and pass along data to Audience Manager. Note the datastream ID, as this ID is required when configuring the Web SDK in code.

+++

+++**2. Install the Web SDK JavaScript library**

See [Install the Web SDK using the JavaScript library](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) for details and code blocks to use. Reference the latest version of `alloy.js` so its method calls can be used.

+++

+++**3. Configure the Web SDK**

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

+++**4. Update code logic to use a JSON payload**

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

+++**5. Update method calls to use the Web SDK**

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

+++**6. Validate and publish changes**

Once you have removed all references to AppMeasurement and the `s` object, publish your changes to your development environment to validate that the new implementation works. Once you have validated that everything works correctly, you can publish your updates to production.

If migrated correctly, `AppMeasurement.js` is no longer required on your site, and all references to this script can be removed.

+++

At this point, your Audience Manager implementation is fully migrated to the Web SDK and is prepared to move to Real-Time CDP in the future.
