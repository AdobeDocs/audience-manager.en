---
description: This article explains how to configure new device-based destinations from the Audience Manager UI.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager UI.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Add New Device-Based Destinations
---

# Add New Device-Based Destinations {#add-new-device-based-destinations}

This article explains how to configure new device-based destinations from the Audience Manager UI.

## Overview {#overview}

The process of adding a new device-based destination consists of two main steps. First, you need to configure the integration between Audience Manager and the destination partner. Once you do that, you can create a new device-based destination.

>[!IMPORTANT]
>
>Not all device-based destinations are eligible for the self-service configuration workflow. If the device-based destination that you need to add is not displayed in the destinations list, contact your Adobe consultant or Customer Support for assistance.

## Step 1. Authenticate with a Destination Platform {#step1}

Before you can create a new device-based destination, you need to configure the integration between Audience Manager and the destination platform. Here's how to do this:

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**. If you have a previously configured integration with a destination platform, you should see it listed in this page. Otherwise, the page is empty.
2. Click **[!DNL Add Account]**.
3. Select the destination platform that you want to authenticate with and click **[!DNL Confirm]** to be redirected to the authentication page of the selected platform. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated to your destination platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.

## Step 2. Create a New Device-Based Destination {#step2}

After you have configured the destination platform integration, you can create the new destination. Here's how to do this:

1. Log in to your Audience Manager account, go to **[!DNL Audience Data > Destinations]**, and click **[!DNL Create Destination]**.
2. In the **[!DNL Basic Information]** section, enter a **[!DNL Name]** and **[!DNL Description]** for your new destination, and use the following settings:

>[!NOTE]
>
>You cannot change the name of an existing device-based destination. Make sure to provide a name that will help you identify the destination correctly.

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: select the destination platform that you want to send audience segments to.
   * **[!DNL Account]**: select the desired advertiser account associated with the selected platform.

![setup](assets/dbd-new-basic.png)

3. Click **[!DNL Next]**.
4. Choose the [Data Export Labels](/help/using/features/data-export-controls.md#controls-labels) that you want to set for this destination.
5. Click **[!DNL Save]**.
6. In the **[!DNL Segment Mappings]** section, select the audience segments that you want to send to this destination.
7. Save the destination.