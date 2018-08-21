---
description: Use the OAuth2 Clients page in the Audience Manager Admin tool to create a new Oauth2 client or to edit an existing client.
seo-description: Use the OAuth2 Clients page in the Audience Manager Admin tool to create a new Oauth2 client or to edit an existing client.
seo-title: Create or Edit an OAuth2 Client
title: Create or Edit an OAuth2 Client
uuid: 8240ab98-3407-47cd-b85e-c9eccd01d071
index: y
internal: n
snippet: y
translate: y
---

# Create or Edit an OAuth2 Client


>1. To create a new OAuth2 client, click **[!UICONTROL  OAuth2 Clients]** > **[!UICONTROL  Add OAuth2 Client]**.

>       Or 

>       To edit an existing OAuth2 client, click the desired client in the **[!UICONTROL  Client ID]** column. 
>1. Specify the desired name for this OAuth2 client.

>       Note that this is a name for the record only. 
>1. Specify the OAuth2 client's email address.

>       There is a limit of one email address. 
>1. From the **[!UICONTROL  Partner]** drop-down list, select the desired partner.
>1. In the **[!UICONTROL  Client ID]** box, specify the desired ID.

>       This is value used when submitting API requests. The prefix auto-populates when you start typing after you have chosen a [!UICONTROL  Partner] from the drop-down list in the preceding step. The correct format is the < *` partner subdomain`*> - < *` Audience Manager username`*&gt;. 
>1. Select or deselect the **[!UICONTROL  Restrict to Partner Users]** check box, as desired.

>       If this check box is selected, the user must be an [!DNL  Audience Manager] user listed for the selected partner. As best practice, we recommend that you select this option. 
>1. In the **[!UICONTROL  Scope]** section, select or deselect the **[!UICONTROL  Read]** and **[!UICONTROL  Write]** check boxes, as desired.
>1. In the **[!UICONTROL  Grant Type]** section, select the desired means for authorization:

>       As best practice, we recommend that you use the default settings of [!UICONTROL  Password] and [!UICONTROL  Refresh-token] options. 
>    
>    * **Implicit: **If you select this option, the [!UICONTROL  Redirect URI] box is enabled. The user is given an automatic access token after being authenticated and is immediately sent to the redirect URI. 

>    * **Authorization Code: **If you select this option, the [!UICONTROL  Redirect URI] box is enabled. The user is returned to the client after being authenticated and is then sent to the redirect URI. 

>    * **Password: **The user is authenticated with a user-entered password rather than an automatic validation attempt via an authorization server. 

>    * **Refresh_token: **Used to refresh an expired access token for an extended period of time. 

>1. In the **[!UICONTROL  Redirect URI]** box, specify the desired URI.

>       This option is enabled only if you select the [!UICONTROL  Implicit] and [!UICONTROL  Authorization_code] grant types. The [!UICONTROL  Redirect URI] box lets you specify a comma-separated value of acceptable URI values. This is the URI a user of a client is redirected to after approving the client for API access. 
>1. Specify the desired expiration time (in seconds) for access and refresh token expiration.

>       **Access Token Expiration Time: **The number of seconds that an access token is valid after being issued. May be null to use the platform default (12 hours). Also may be -1 to indicate that the access token does not expire. 

>       **Refresh Token Expiration Time: **The number of seconds that a refresh token is valid after being issued. May be null to use the platform default (30 days). 
>1. Click **[!UICONTROL  Save]**.
>[!MORE_LIKE_THIS]
>
>* [ API Requirements and Recommendations ](aam-admin-api-requirements.md#concept_A7FAC9443CF34974A873E6B787616421)
