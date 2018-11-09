---
description: Use the Servers page in the Audience Manager Admin tool to create a new HTTP server or to edit an existing server.
seo-description: Use the Servers page in the Audience Manager Admin tool to create a new HTTP server or to edit an existing server.
seo-title: Create or Edit an HTTP Server
title: Create or Edit an HTTP Server
uuid: 6fcdd666-32c2-4cb2-9e44-3df0fd4506fc
index: y
internal: n
snippet: y
---

# Create or Edit an HTTP Server{#create-or-edit-an-http-server}

Use the Servers page in the Audience Manager Admin tool to create a new HTTP server or to edit an existing server.

>[!NOTE]
>
>You must have the [!UICONTROL DEXADMIN] role in order to create new servers or edit existing servers.

1. To create a new server, click **[!UICONTROL Servers]** > **[!UICONTROL Create Server]**.

   Or

   To edit an existing server, click the desired server in the **[!UICONTROL Label]** column. 
1. Specify the desired label for this server.
1. From the **[!UICONTROL Protocol]** drop-down list, select the desired protocol: **HTTP**.
1. Fill in the fields:

   **Domain: **Specify the desired domain (host) for this server.

   **Port: **Specify the desired port for this server. The default port displays for each encryption type. You can change the default port, if necessary

   **Maximum Users Per Request: **Specify the maximum number of users per request allowed for this server.

   **URL Prefix: **Specify the URL prefix to use for this server.

   **Authentication URL: **Specify the Authentication URL for this HTTP server.

   **Authentication: **Specify the desired authentication method: **[!UICONTROL None]**, **[!UICONTROL Username/Password]**, or **[!UICONTROL SSH Key]**.

   **HTTP Signature Header:** The name of the HTTP header, provided by the customer, that contains the HTTP signature key. The default value is X-Signature, as shown in the example below:

   ```
   * Connected to partner.website.com (127.0.0.1) port 80 (#0)
   > POST /webpage HTTP/1.1
   > Host: partner.host.com
   > Accept: */*
   > Content-Type: application/json
   > Content-Length: 20
   > X-Signature: wxa2ByMWhhP328EvHQsVlOD5jTc=
   POST message content
   ```

   **HTTP Signature Key:** The key used to sign the HTTP request, provided by the customer.

   **Show Signature Key:** Toggle whether or not to display the signature in the browser.

   **HTTP Signature Encryption Method:** Specify the method we use for encrypting the signature. Use SHA1 unless the customer prefers otherwise.

   >[!NOTE] {importance="normal"}
   >
   >If you want to enable [OAuth 2.0 authentication for real-time data transfers](https://marketing.adobe.com/resources/help/en_US/aam/oauth-in-outbound-transfers.html) for a partner, fill in the fields as in the table below. The fields in *italics* need to be filled in exactly as in the table.

   |  Name  | Value  |
   |---|---|
   |  Label  | Server with OAuth 2.0 enabled  |
   |  Protocol  | HTTP  |
   |  Domain  | api.partner.com  |
   |  Port  | 443  |
   |  Maximum Users per Request  | 10  |
   |  URL Prefix  | /segments/aam  |
   |  Authentication URL  | api.partner.com/oauth2/token  |
   |  Authentication  | Username/Password  |
   |  Username  |*Authorization* |
   |  Password  |*Basic* your_password_here  |
   |  HTTP Signature Header  | Leave this field blank  |
   |  HTTP Signature Key  | Leave this field blank  |
   |  HTTP Signature Encryption Method  | None  |

1. Click **[!UICONTROL Create]** if you are creating a new server.

   Or

   Click **[!UICONTROL Update]** if you are editing an existing server. 

