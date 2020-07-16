---
description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Add New Device-Based Destinations
feature: Destination Basics
---

# Add New Device-Based Destinations {#add-new-device-based-destinations}

This article explains how to configure new device-based destinations from the Audience Manager user interface.

>[!IMPORTANT]
>
>Currently, most device-based destinations are not eligible for the self-service configuration workflow. If the device-based destination that you need to add is not displayed in the destinations list, contact your Adobe consultant or Customer Support for assistance.

## Overview {#overview}

The process of adding a new device-based destination consists of two main steps. First, you need to configure the integration between Audience Manager and the destination partner. Once you do that, you can create a new device-based destination.

## Prerequisites {#prerequisites}

When creating the first device-based destination with an integrated platform, please contact Adobe Consulting or Customer Care to enable ID synchronization between Audience Manager and the integrated platform for your account. This is required for the correct synchronization between Audience Manager and the destination platform.

## Step 1. Authenticate with a Destination Platform {#step1}

Before you can create a new device-based destination, you need to configure the integration between Audience Manager and the destination platform. Here's how to do this:

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**. If you have a previously configured integration with a destination platform, you should see it listed in this page. Otherwise, the page is empty.
1. Click **[!DNL Add Account]**.
1. Select the destination platform that you want to authenticate with and click **[!DNL Confirm]** to be redirected to the authentication page of the selected platform.

   ![integrated-platforms](assets/dbd-integrated-platforms.png)

1. Once you've authenticated to your destination platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.

## Step 2. Create a New Device-Based Destination {#step2}

After you have configured the destination platform integration, you can create the new destination. Here's how to do this:

>[!NOTE]
>
>You cannot change the name of an existing device-based destination. Make sure to provide a name that will help you identify the destination correctly.

1. Log in to your Audience Manager account, go to **[!DNL Audience Data > Destinations]**, and click **[!DNL Create Destination]**.
1. In the **[!DNL Basic Information]** section, enter a **[!DNL Name]** and **[!DNL Description]** for your new destination, and use the settings in the list below:

   ![setup](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: select the destination platform that you want to send audience segments to.
   * **[!DNL Account]**: select the desired advertiser account associated with the selected platform.
1. Click **[!DNL Next]**.
1. Choose the [Data Export Labels](/help/using/features/data-export-controls.md#controls-labels) that you want to set for this destination.
1. Click **[!DNL Save]**.
1. In the **[!DNL Segment Mappings]** section, select the audience segments that you want to send to this destination.
1. Save the destination.
