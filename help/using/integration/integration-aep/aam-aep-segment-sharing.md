---
description: This article describes how segments are shared between Audience Manager and Adobe Experience Platform.
seo-description: This article describes how segments are shared between Audience Manager and Adobe Experience Platform.
seo-title: Segment Sharing Between Audience Manager and Adobe Experience Platform
solution: Audience Manager
title: Segment Sharing Between Audience Manager and Adobe Experience Platform
keywords: AEP segment sharing, AEP segments, Platform segments
---

# Segment Sharing Between Audience Manager and Adobe Experience Platform {#aam-aep-segment-sharing}

>[!NOTE]
>
>This page contains beta documentation that is available to customers of Audience Manager and Adobe Experience Platform and is subject to change before the final product release.

## Overview {#overview}

The segment sharing functionality between Audience Manager and Adobe Experience Platform allows you to use your Audience Manager segments in Adobe Experience Platform and vice-versa.

You can use Audience Manager segments in Experience Platform to add Audience Manager data to your customer profiles and to benefit from the Experience Platform [segmentation service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md).

Use Experience Platform segments in Audience Manager for Data Management Platform use cases, such as:
* Adding [third party data](/help/using/overview/data-types-collected.md#third-party-data) to your segments;
* [Algorithmic modeling](/help/using/features/algorithmic-models/understanding-models.md);
* Activating your segments to destinations not supported in the Experience Platform.

![Use Cases](/help/using/integration/integration-aep/assets/aam-aep-usecases.png)

## Audience Manager segments in Adobe Experience Platform {#aam-segments-in-aep}

For information on how your Audience Manager segments appear and can be used in Experience Platform, see:

* [Audience Manager Connector documentation](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/audience_manager_connector.md)
* another link
* yet another link

## Adobe Experience Platform segments in Audience Manager {#aep-segments-in-aam}

Segments that you create in Experience Platform appear in your Audience Manager interface as traits and segments, with the following composition rules:
* The trait rule is the ID of the Experience Platform segment.
The Audience Manager segments consist of the trait;
* The segment consists of the trait described above. 

### Traits {#aep-segments-as-aam-traits}

Audience Manager automatically creates a trait folder called **Experience Platform Traits** in your trait storage.  

![Traits from Experience Platform dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

You can use automatically created traits in segments alongside other traits. For example, you can mix traits created from Experience Platform segments with third party traits acquired through the Audience Marketplace.

For an example of a trait created automatically from an Experience Platform segment, see the screenshot below:

![Trait from Experience Platform](/help/using/integration/integration-aep/assets/aep-trait-numbered.png)


Item number | Name | Description
---------|----------|---------
 1 | Trait Type | Traits created from Experience Platform segments are created as onboarded traits in Audience Manager
 2 | Data Source | Automatically created. All traits and segments created that are created automatically from Experience Platform segments are stored in the data source **Adobe Experience Platform Audience Sharing** 
 3 | Integration Code | The integration code corresponds to the segment ID in Experience Platform
 4 | Trait Expression | The trait expression is `segID = segment ID in Experience Platform`
 5 | Segments with this Trait | An automatically created segment that uses this trait as its composition. 

### Segments {#aep-segments-as-aam-segments}

Screenshot of dashboard

Screenshot of segment