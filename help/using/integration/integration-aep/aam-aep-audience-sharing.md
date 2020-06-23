---
description: This article describes how audiences are shared between Audience Manager and Adobe Experience Platform.
seo-description: This article describes how audiences are shared between Audience Manager and Adobe Experience Platform.
seo-title: Audience Sharing Between Audience Manager and Adobe Experience Platform
solution: Audience Manager
title: Audience Sharing Between Audience Manager and Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
---

# Audience Sharing Between Audience Manager and Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contact your Adobe sales representative to unlock access to this functionality.

## Overview {#overview}

The audience sharing functionality between Audience Manager and Adobe Experience Platform allows you to share your Audience Manager traits and segments to Adobe Experience Platform and vice-versa. You need the [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) to enable audience sharing between Audience Manager and Adobe Experience Platform.

You can use Audience Manager traits and segments in Experience Platform to add Audience Manager data to your customer profiles and to benefit from the Experience Platform [segmentation service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md). 

In Audience Manager, you can use Experience Platform segments for Data Management Platform use cases, such as:
* Add [third party data](/help/using/overview/data-types-collected.md#third-party-data) to your segments;
* [Algorithmic modeling](/help/using/features/algorithmic-models/understanding-models.md);
* Activate your segments to destinations that are not yet supported in the Experience Platform [destinations catalog](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Additionally, your Experience Platform segments are shared to other Experience Cloud solutions, via [Core Services](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br>&nbsp;

See the table below for an overview of audience sharing use cases:

**Use Case** | **Adobe Experience Platform** | **Audience Manager** | **Core Services**
---------|----------|---------|---------
 **Audience Sharing** | <ul><li>Enrich customer profiles with Audience Manager data</li><li>Use Audience Manager data in Experience Platform segmentation</li></ul> | <ul><li>Add third party data to segments</li><li>Algorithmic modeling</li><li>Activation to additional destinations</li></ul> | Use Experience Platform segments in other Experience Cloud solutions, such as Adobe Target or Analytics.

<br>&nbsp;

## Audience Manager segments and traits in Adobe Experience Platform {#aam-segments-traits-in-aep}

Your Audience Manager traits and segments appear in Experience Platform as **Audiences** in the segment workflow. For more information on your Audience Manager segments and traits in Experience Platform, see:

* [Segmentation Service overview](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform Segment Builder user guide](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br>&nbsp;

## Adobe Experience Platform segments in Audience Manager {#aep-segments-in-aam}

Segments that you create in Experience Platform appear in your Audience Manager interface as traits and segments, with the following composition rules:
* Trait: The trait rule is the ID of the Experience Platform segment.
* Segment: The segment consists of the trait described above.

### Traits {#aep-segments-as-aam-traits}

Audience Manager automatically creates a trait folder called **Experience Platform Traits** in your trait storage.  

![Traits from Experience Platform dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

You can use automatically created traits in segments alongside other traits. For example, you can mix traits created from Experience Platform segments with third party traits acquired through the [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

For an example of a trait created automatically from an Experience Platform segment, see the screenshot below: 

![Trait from Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


Item number | Name | Description
---------|----------|---------
 1 | [!UICONTROL Trait Type] | Traits created from Experience Platform segments are created as onboarded traits in Audience Manager.
 2 | [!UICONTROL Data Source] | Automatically created. All traits and segments that are created automatically from Experience Platform segments are stored in the data source **[!UICONTROL Adobe Experience Platform Audience Sharing]**.
 3 | [!UICONTROL Integration Code] | The integration code corresponds to the segment ID in Experience Platform.
 4 | [!UICONTROL Trait Expression] | The trait expression is `segID = segment ID in Experience Platform`.
 5 | [!UICONTROL Segments with this Trait] | An automatically created segment that uses this trait as its composition.

<br>&nbsp;

### Segments {#aep-segments-as-aam-segments}

Audience Manager automatically creates a segment folder called **Experience Platform Segments** in your segment storage.

![Screenshot of dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

For an example of a segment created automatically from an Experience Platform segment, see the screenshot below:

![Screenshot of segment](/help/using/integration/integration-aep/assets/aep-segment.png)

Item number | Name | Description
---------|----------|---------
 1 | [!UICONTROL Integration Code] | The integration code corresponds to the segment ID in Experience Platform.
 2 | [!UICONTROL Data Source] | Automatically created. All traits and segments that are created automatically from Experience Platform segments are stored in the data source **[!DNL Adobe Experience Platform Audience Sharing]**.
 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indicates that automatically created segments follow the merge policy set up in Experience Platform.
 4 | [!UICONTROL Segment Rule] | The segment consists of the trait described in the [Traits section](#aep-segments-as-aam-traits).

## Audience Manager Data Export Control support in Experience Platform {#aam-data-export-control-in-aep}

In order to enforce data usage compliance in Experience Platform, all applicable datasets and fields must be given appropriate [data usage labels](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html). In addition, [data usage policies](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) must be enabled for specific marketing actions against those labels, as outlined by the [Data Usage Labeling and Enforcement (DULE) framework](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

In the audience sharing process between Audience Manager and Experience Platform, any Data Export Controls that have been applied to Audience Manager segments are translated to equivalent labels and marketing actions recognized by Experience Platform Data Governance, and vice versa.

>[!NOTE] For more general information on Data Export Controls, please refer to the [Data Export Controls documentation](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
This document provides a reference for how specific Audience Manager Data Export Controls map to data usage labels and marketing actions in Platform.

### Data Export Controls to data usage labels

The following table outlines how specific Data Export Controls map to recognized data usage labels:

| Data Export Control | Data usage label |
| --- | --- |
| Cannot be used with personally identifiable information | C3: Data cannot be combined or otherwise used with directly identifiable information |
| Cannot be used for offsite ad targeting | C5: Data cannot be used for interest-based, cross-site targeting of content or ads |
| Cannot be used for onsite ad targeting | C6: Data cannot be used for on-site ad targeting |
| Cannot be used for onsite personalization | C7: Data cannot be used for on-site targeting of content |

### Data Export Controls to marketing actions

The following table outlines how specific Data Export Labels map to recognized marketing actions:

| Data Export Label | Marketing action |
| --- | --- |
| This destination may enable a combination with personally identifiable information (PII) | Combine with PII |
| This destination may be used for off-site ad targeting | Cross Site Targeting |
| This destination may be used for on-site ad targeting | Onsite Advertising |
| This destination may be used for on-site ad personalization | Onsite Personalization |

## Understand segment population differences between Audience Manager and Experience Platform 

Segment population numbers can vary between your Audience Manager and Experience Platform segments. While segment numbers for similar or identical audiences should be close, differences in populations can be due to:

* Segmentation jobs run times. Audience Manager runs a segmentation job that updates the numbers in the interface once per day. This job rarely aligns with the segmentation jobs in Experience Platform.
* [Profile Merge Rules](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager and [Merge Policies](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in Experience Platform work differently, and the identity graph used for each varies. Because of this, some differences between segment populations are expected.

>[!MORELIKETHIS]
>
>* [Segmentation Service overview](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform Segment Builder user guide](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) 