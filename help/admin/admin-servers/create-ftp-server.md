---
description: Use the Servers page in the Audience Manager Admin tool to create a new FTP server or to edit an existing server.
seo-description: Use the Servers page in the Audience Manager Admin tool to create a new FTP server or to edit an existing server.
seo-title: Create or Edit an FTP Server
title: Create or Edit an FTP Server
uuid: 9273abb2-963d-4d83-bf5a-b3817f0b90e6
---

# Create or Edit an FTP Server{#create-or-edit-an-ftp-server}

Use the Servers page in the Audience Manager Admin tool to create a new FTP server or to edit an existing server.

>[!NOTE]
>
>You must have the [!UICONTROL DEXADMIN] role in order to create new servers or edit existing servers.

1. To create a new server, click **[!UICONTROL Servers]** > **[!UICONTROL Create Server]**.

   Or

   To edit an existing server, click the desired server in the **[!UICONTROL Label]** column.
1. Specify the desired label for this server.
1. From the **[!UICONTROL Protocol]** drop-down list, select the desired protocol: **FTP**.

   >[!NOTE]
   >
   >As best practice, we recommend using [!UICONTROL Amazon S3] as a method for getting files from and delivering files to partners. Amazon S3 provides a simple web services interface that can be used to store and retrieve any amount of data, at any time, from anywhere on the web. For more information, see [About Amazon S3](https://microsite.omniture.com/t2/help/en_US/demdex/index.html#About_Amazon_S3) in the *Audience Manager Product Documentation*.

1. Fill in the fields:

   **Type:** Select the desired encryption type: **[!UICONTROL SFTP]** or **[!UICONTROL FTPs/TLS]**.

   **Domain:** Specify the desired domain (host) for this server.

   **Port:** Specify the desired port for this server. The default port displays for each encryption type. You can change the default port, if necessary.

   **Remote Path:** Specify the desired remote path for this server. If you leave this field empty, Audience Manager places the files in the default directory.

   **.tmp File Rename on Completion:** Enable this option to rename the .tmp file on completion.

   **Filename Suffix:** Specify the text that you want appended to transfer files.

   **Moved to When Finished:** Specify the path to the location where you want the transfer file moved on completion.

   **Authentication:** Specify the desired server authentication method: **[!UICONTROL Username/Password]** or **[!UICONTROL SSH Key]**.

   >[!NOTE]
   >
   >Remember to whitelist our egress FTP IP: **52.44.29.204**.

1. For **[!UICONTROL SSH Key]** authentication:
   1. Generate the public / private key pair from any Linux or Mac machine.
   2. Give the **public key** to the client to update on their SFTP server. They must include all the text from the public key on their server, including `-----BEGIN RSA PRIVATE KEY-----` & `-----END RSA PRIVATE KEY-----` . In exchange, they must provide the username under which they are installing the key.
   3. Update the username field with the one provided by the client and the key field with the **private key**.
1. Click **[!UICONTROL Create]** if you are creating a new server.

   Or

   Click **[!UICONTROL Update]** if you are editing an existing server.
