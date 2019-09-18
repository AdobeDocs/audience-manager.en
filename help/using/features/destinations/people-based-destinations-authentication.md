---
description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms. 
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms. 
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Authentication with People-Based Platforms
---

# Authentication with People-Based Platforms {#authentication-with-people-based-platforms}

This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.

>[!NOTE]
>This is a mandatory step for People-Based Destinations, regardless of your implementation scenario.

## Configure People-Based Platform Authentication {#configure-authentication}

1. Log in to your Audience Manager account and go to **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. If you have a previously configured integration with a social platform, you should see it listed in this page. Otherwise, the page is empty.
    ![people-based-integration](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. Use the **[!UICONTROL People-Based Platform]** drop-down menu to select the platform that you want to configure the integration with.
    ![people-based-platform](assets/pbd-add.png)
1. Click **[!UICONTROL Confirm]** to be redirected to the authentication page of the selected platform.
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!UICONTROL Confirm]**.
1. Audience Manager displays a notification at the top of the page to let you know whether the account was successfully added. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

## Authentication Token Expiration and Notification Management {#token-expiration-notification}

Audience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. Token validity duration is subject to each social platform's integration rules. Once the authentication token expires, Audience Manager is unable to send your audience segments to your destination. To avoid this scenario, we recommend adding at least one contact email address to your integration, so that you get notified as soon as the authentication token is about to expire. When that happens, you can re-authenticate to ensure the destination continues to receive your audience segments.

Here's how to add email addresses to existing integrations:

1. Log in to your Audience Manager account and go to **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identify the integration that you want to receive token expiration notifications for, and click the **[!UICONTROL Edit]** icon.
1. Enter the email addresses that you want to receive token expiration notifications, separated by commas.
1. Click **[!UICONTROL Save]**.

## Authentication Token Renewal {#token-renewal}

When an authentication token expires, the integration between Audience Manager and the corresponding social platform is interrupted, so Audience Manager cannot send audience segments to the destination anymore. The [!UICONTROL Integrated Accounts] page shows you the expiration status of each integration in the [!UICONTROL Expiration] column, and allows you to renew the authentication at any time.

Here's how to renew an expired or about-to-expire authentication:
1. Log in to your Audience Manager account and go to **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identify the integration that you need to renew authentication for. Expired authentications are marked as [!UICONTROL Expired], while authentications that are about to expire soon show the remaining number of authenticated days.
1. Click the corresponding **[!UICONTROL Renew]** icon in the [!UICONTROL Expiration] column. This triggers the **[!UICONTROL Renew Account]** workflow, which takes you back through the social platform's authentication page. Once you authenticate, the token is renewed with the new expiration date.
   ![pbd-renew](assets/pbd-renew.png)
