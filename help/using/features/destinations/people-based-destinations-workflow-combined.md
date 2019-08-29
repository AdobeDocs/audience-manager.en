---
description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.  
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.   
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
---

# Workflow A - Personalization Based on All Online Activity Combined with Offline Data {#workflow-a}

This page includes step-by-step guidance on how to combine offline [!DNL CRM] data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to [!DNL People-Based Destinations].

## Step 1 - Configure Data Source Settings {#configure-data-source-settings}

Depending on whether your [DPUUIDs](../../reference/ids-in-aam.md) are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.

**Scenario 1: your [DPUUIDs](../../reference/ids-in-aam.md) are already lowercase, hashed email addresses.**

In this case, you need to need to label the corresponding data source as such:

1. Go to [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Find the data source that contains your [DPUUIDs](../../reference/ids-in-aam.md), and click it.
1. Make sure the option [!UICONTROL Cannot be tied to personally identifiable information] is unchecked.
1. Save the data source settings.

**Scenario 2: your [DPUUIDs](../../reference/ids-in-aam.md) are not lowercase, hashed email addresses.**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. Here's how to do this:

1. Log in to your Audience Manager account and go to **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, and click **[!UICONTROL Add New]**.
1. Enter a [!UICONTROL Name] and [!UICONTROL Description] for your new data source.
1. In the **[!UICONTROL ID Type]** drop-down menu, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL Data Source Settings]** section, select both the **[!UICONTROL Inbound]** and **[!UICONTROL Outbound]** options, and enable the **[!UICONTROL Share associated cross-device IDs in people-based destinations]** option.
1. Use the drop-down menu to select the **[!UICONTROL Emails(SHA256, lowercased)]** label for this data source.
    >[!IMPORTANT]
    >
    >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the [!DNL SHA256] algorithm. Otherwise, you won't be able to use it for [!DNL People-Based Destinations].

    ![pbd-datasource-settings](assets/pbd-ds-config.png)

>[!NOTE]
>
> See [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding) for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.

## Step 2 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to [Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) described above. If your existing [DPUUIDs](../../reference/ids-in-aam.md) are already hashed email addresses, skip to [Step 3 - Create a Profile Merge Rule for Segmentation](people-based-destinations-workflow-combined.md#create-merge-rule).

Let's say you want to match your existing [DPUUIDs](../../reference/ids-in-aam.md) to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at [Step 1 - Configure Data Source Settings](people-based-destinations-workflow-combined.md#configure-data-source-settings). 

| DPUUID (CRM ID) | Email address | Hashed email address |
| --- | --- | --- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` |feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

You can link up to 10 hashed email addresses to a single [DPUUID](../../reference/ids-in-aam.md). To do this, separate the hashed email addresses with a comma, inside the synchronization file.

In our example, you would now have two data sources.

| Data source ID | Data source contents |
| --- | --- |
|999999|Existing DPUUIDs (CRM IDs) |
|987654|Hashed email addresses |

Your [ID synchronization file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) would have the following contents:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

The [ID synchronization file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) must follow this naming structure:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

In the example above, the file name would look like this:
`c2c_id_999999_987654_1560431657.sync`

[Download example file here](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Step 3 - Create a Profile Merge Rule for Segmentation {#create-merge-rule}

The next step is creating a new merge rule that will help you create the audience segments to send to your people-based destinations.

>[!IMPORTANT]
>
> If you already have a rule defined with the [!UICONTROL Current Authenticated Profiles] or [!UICONTROL Last Authenticated Profiles] options, you can skip to [Step 4 - Create Audience Segments](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Log in to your Audience Manager account and go to **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Click **[!UICONTROL Add New Rule]**.
1. Enter a profile merge rule **[!UICONTROL Name]** and **[!UICONTROL Description]**.
1. In the **[!UICONTROL Profile Merge Rule Setup]** section, select the **[!UICONTROL Current Authenticated Profiles]** or **[!UICONTROL Last Authenticated Profiles]** options.
1. In the **[!UICONTROL Cross-Device Profile Options]** list, select the data sources that you want to run the segmentation on. These should be the data sources containing your existing [DPUUIDs](../../reference/ids-in-aam.md).

## Step 4 - Create Audience Segments {#create-audience-segments}

To create new audience segments, use the [Segment Builder](../segments/segment-builder.md). If you have existing audience segments that you want to send to [!DNL People-Based Destinations], skip to [Step 5 - Configure People-Based Platform Authentication](people-based-destinations-workflow-combined.md#configure-authentication).

## Step 5 - Configure People-Based Platform Authentication {#configure-authentication}

1. Log in to your Audience Manager account and go to **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. If you have a previously configured integration with a social platform, you should see it listed in this page. Otherwise, the page is empty.
    ![people-based-integration](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. Use the **[!UICONTROL People-Based Platform]** drop-down menu to select the platform that you want to configure the integration with.
    ![people-based-platform](assets/pbd-add.png)
1. Click **[!UICONTROL Confirm]** to be redirected to the authentication page of the selected platform.
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!UICONTROL Confirm]**.
1. Audience Manager displays a notification at the top of the page to let you know whether the account was successfully added. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. See Authentication Token Renewal for details on how to renew the expired tokens.

## Step 6 - Create a People-Based Destination {#create-destination}

1. Log in to your Audience Manager account, go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**, and click **[!UICONTROL Create Destination]**.
1. In the **[!UICONTROL Basic Information]** section, enter a **[!UICONTROL Name]** and **[!UICONTROL Description]** for your new data source, and use the following settings:
    * **[!UICONTROL Category]**: Integrated Platforms;
    * **[!UICONTROL Type]**: People-Based;
    * **[!UICONTROL Platform]**: select the people-based platform that you want to send audience segments to;
    * **[!UICONTROL Account]**: select the desired advertiser account associated with the selected platform.
    ![create-destination](assets/pbd-create-destination.png)
1. Click **[!UICONTROL Next]**.
1. Choose the **[!UICONTROL Data Export Labels]** that you want to set for this destination.
1. In the **[!UICONTROL Configuration]** section, select the data source that contains your hashed data sources.
1. In the **[!UICONTROL Segment Mappings]** section, select the segments that you want to send to this destination. This would be the segments that you created at [Step 4 - Create Audience Segments](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Save the destination.
