---
description: Use the OAuth2 Clients page to view a list of OAuth2 clients in your Audience Manager configuration. You can edit or delete existing clients or create new clients, providing that you have the appropriate user roles assigned.
seo-description: Use the OAuth2 Clients page to view a list of OAuth2 clients in your Audience Manager configuration. You can edit or delete existing clients or create new clients, providing that you have the appropriate user roles assigned.
seo-title: OAuth2 Clients
title: OAuth2 Clients
uuid: 162acf2a-3e8c-4d98-b510-5ab83cf7a23b
index: y
internal: n
snippet: y
---

# OAuth2 Clients{#oauth-clients}

Use the OAuth2 Clients page to view a list of OAuth2 clients in your Audience Manager configuration. You can edit or delete existing clients or create new clients, providing that you have the appropriate user roles assigned.

## OAuth2 Clients {#concept_8685EBB8F0C04295A3607DA6016293E2}

Use the [!UICONTROL OAuth2 Clients] page to view a list of [!UICONTROL OAuth2] clients in your [!DNL Audience Manager] configuration. You can edit or delete existing clients or create new clients, providing that you have the appropriate user roles assigned.

<!-- 

c_oauth.xml

 -->

>[!NOTE]
>
>Ensure that your customer reads the [OAuth2](https://marketing.adobe.com/resources/help/en_US/aam/oauth-authentication.html) documentation in the Audience Management User Guide.

[!UICONTROL OAuth2] is an open standard for authorization to provide secured delegated access to [!DNL Audience Manager] resources on behalf of a resource owner.

![](assets/oauth.png)

You can sort each column in ascending or descending order by clicking the desired column's header.

Use the [!UICONTROL Search] box or the pagination controls at the bottom of the list to find the desired client. 

## Create or Edit an <wintitle> OAuth2 </wintitle> Client {#task_5217A96A299C466CA601313D920A32E5}

Use the [!UICONTROL OAuth2 Clients] page in the [!DNL Audience Manager] Admin tool to create a new [!UICONTROL Oauth2] client or to edit an existing client.

1. 

   <!-- 

t_create_edit_auth.xml

 -->

   To create a new [!UICONTROL OAuth2] client, click **[!UICONTROL OAuth2 Clients]** > **[!UICONTROL Add OAuth2 Client]**.

   Or

   To edit an existing [!UICONTROL OAuth2] client, click the desired client in the **[!UICONTROL Client ID]** column. 
1. Specify the desired name for this [!UICONTROL OAuth2] client.

   Note that this is a name for the record only. 
1. Specify the [!UICONTROL OAuth2] client's email address.

   There is a limit of one email address. 
1. From the **[!UICONTROL Partner]** drop-down list, select the desired partner.
1. In the **[!UICONTROL Client ID]** box, specify the desired ID.

   This is value used when submitting API requests. The prefix auto-populates when you start typing after you have chosen a [!UICONTROL Partner] from the drop-down list in the preceding step. The correct format is the < *`partner subdomain`*> - < *`Audience Manager username`*>. 
1. Select or deselect the **[!UICONTROL Restrict to Partner Users]** check box, as desired.

   If this check box is selected, the user must be an [!DNL Audience Manager] user listed for the selected partner. As best practice, we recommend that you select this option. 
1. In the **[!UICONTROL Scope]** section, select or deselect the **[!UICONTROL Read]** and **[!UICONTROL Write]** check boxes, as desired.
1. In the **[!UICONTROL Grant Type]** section, select the desired means for authorization:

   As best practice, we recommend that you use the default settings of [!UICONTROL Password] and [!UICONTROL Refresh-token] options.

* **[!UICONTROL Implicit]**: If you select this option, the [!UICONTROL Redirect URI] box is enabled. The user is given an automatic access token after being authenticated and is immediately sent to the redirect URI. 
* **[!UICONTROL Authorization Code]**: If you select this option, the [!UICONTROL Redirect URI] box is enabled. The user is returned to the client after being authenticated and is then sent to the redirect URI. 
* **[!UICONTROL Password]**: The user is authenticated with a user-entered password rather than an automatic validation attempt via an authorization server. 
* **[!UICONTROL Refresh_token]**: Used to refresh an expired access token for an extended period of time.

1. In the **[!UICONTROL Redirect URI]** box, specify the desired URI.

   This option is enabled only if you select the **[!UICONTROL Implicit]** and **[!UICONTROL Authorization_code]** grant types. The **[!UICONTROL Redirect URI]** box lets you specify a comma-separated value of acceptable URI values. This is the URI a user of a client is redirected to after approving the client for API access. 
1. Specify the desired expiration time (in seconds) for access and refresh token expiration.

   **[!UICONTROL Access Token Expiration Time]**: The number of seconds that an access token is valid after being issued. May be null to use the platform default (12 hours). Also may be -1 to indicate that the access token does not expire.

   **[!UICONTROL Refresh Token Expiration Time]**: The number of seconds that a refresh token is valid after being issued. May be null to use the platform default (30 days). 
1. Click **[!UICONTROL Save]**.
To delete an [!UICONTROL OAuth2] client, click **[!UICONTROL OAuth2 Clients]**, then click  ![](assets/icon_delete.png) in the **[!UICONTROL Actions]** column for the desired client. 

>[!MORE_LIKE_THIS]
>
>* [API Requirements and Recommendations](aam-admin-api-requirements.md#concept_A7FAC9443CF34974A873E6B787616421)
