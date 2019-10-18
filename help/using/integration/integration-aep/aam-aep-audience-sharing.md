---
description: This article describes how audiences are shared between Audience Manager and Adobe Experience Platform.
seo-description: This article describes how audiences are shared between Audience Manager and Adobe Experience Platform.
seo-title: Audience Sharing Between Audience Manager and Adobe Experience Platform
solution: Audience Manager
title: Audience Sharing Between Audience Manager and Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments
---

# Audience Sharing Between Audience Manager and Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
>This page contains beta documentation that describes functionality available to customers of Audience Manager *and* Adobe Experience Platform. This documentation is subject to change before the final product release.
>
> Contact your Adobe sales representative to unlock access to this functionality.

## Overview {#overview}

The audience sharing functionality between Audience Manager and Adobe Experience Platform allows you to share your Audience Manager traits and segments to Adobe Experience Platform and vice-versa.

You can use Audience Manager traits and segments in Experience Platform to add Audience Manager data to your customer profiles and to benefit from the Experience Platform [segmentation service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md). 

In Audience Manager, you can use Experience Platform segments for Data Management Platform use cases, such as:
* Adding [third party data](/help/using/overview/data-types-collected.md#third-party-data) to your segments;
* [Algorithmic modeling](/help/using/features/algorithmic-models/understanding-models.md);
* Activating your segments to destinations not currently supported in the Experience Platform.

Additionally, your Experience Platform segments are shared to other Experience Cloud solutions, via [Core Services](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br>&nbsp;

See the table below for an overview of audience sharing use cases:

`*` | **Adobe Experience Platform** | **Audience Manager** | **Core Services**
---------|----------|---------|---------
 **Audience Sharing Use Case** | <ul><li>Enrich customer profiles with Audience Manager data</li><li>Use Audience Manager data in Experience Platform segmentation</li></ul> | <ul><li>Add third party data to segments</li><li>Algorithmic modeling</li><li>Activation to additional destinations</li></ul> | Use Experience Platform segments in other Experience Cloud solutions, such as Adobe Target or Analytics.

<br>&nbsp;

## Audience Manager segments and traits in Adobe Experience Platform {#aam-segments-traits-in-aep}

Your Audience Manager traits and segments appear in Experience Platform as **Audiences** in the segment workflow. For more information on your Audience Manager segments and traits in Experience Platform, see:

* [Segmentation Service overview](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [Experience Platform Segment Builder user guide](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

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

![Trait from Experience Platform](/help/using/integration/integration-aep/assets/aep-trait-numbered.png)


Item number | Name | Description
---------|----------|---------
 1 | Trait Type | Traits created from Experience Platform segments are created as onboarded traits in Audience Manager.
 2 | Data Source | Automatically created. All traits and segments that are created automatically from Experience Platform segments are stored in the data source **Adobe Experience Platform Audience Sharing**.
 3 | Integration Code | The integration code corresponds to the segment ID in Experience Platform.
 4 | Trait Expression | The trait expression is `segID = segment ID in Experience Platform`.
 5 | Segments with this Trait | An automatically created segment that uses this trait as its composition. 

<br>&nbsp;

### Segments {#aep-segments-as-aam-segments}

Audience Manager automatically creates a segment folder called **Experience Platform Segments** in your segment storage. 

![Screenshot of dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

For an example of a segment created automatically from an Experience Platform segment, see the screenshot below:

![Screenshot of segment](/help/using/integration/integration-aep/assets/aep-segment-numbered.png)

Item number | Name | Description
---------|----------|---------
 1 | Integration Code | The integration code corresponds to the segment ID in Experience Platform.
 2 | Data Source | Automatically created. All traits and segments that are created automatically from Experience Platform segments are stored in the data source **Adobe Experience Platform Audience Sharing**.
 3 | Profile Merge Rule | The segment uses an automatically created [Profile Merge Rule](/help/using/features/profile-merge-rules/merge-rules-overview.md), with the **No Cross-Device Profile** and **Device Profile** options.
 4 | Segment Rule | The segment consists of the trait described in the [Traits section](#aep-segments-as-aam-traits).