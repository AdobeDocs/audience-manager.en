---
description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Instant Cross-Device Suppression
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
---

# Instant Cross-Device Suppression {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.

## Overview {#overview}

[!UICONTROL Instant Cross-Device Suppression] delivers two key use cases: improved user experience and media efficiency.

* **An improved user experience**: Users that already purchased your product or service will not see the same creatives as before the purchase. Instead, you could display upselling or cross-selling messages for products or services that you know they have not purchased.
* **Media efficiency**: Optimize your campaign spending by applying a global frequency cap across all [!DNL DSP]s. The frequency cap can be actioned in real-time for multiple devices belonging to a user.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](merge-rule-unsegment.md). Read on for the practical implementation of the use cases described above.

## Do Not Target Once Converted {#do-not-target-once}

Assure that your users that have already converted (purchased a product, acquired a subscription, etc.) will not see the same messaging as before the conversion. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. You must use a rule-based trait to define the conversion event for the unsegment to be triggered in real-time. Read more about how to [create rule-based traits](../traits/create-onboarded-rule-based-traits.md).
2. Map the segment to any number of real-time server-to-server destinations. Read on about how to add segments to [server-to-server destinations](../destinations/add-edit-segments.md).

Your visitors qualify for the segment as long as they have not converted. As soon as they qualify for the conversion trait, they cease to follow the segment rule and are instantly removed from the segment.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

You can make sure you are not flooding your users with the same creative by setting recency and frequency controls. In this scenario, create a segment with two traits, as outlined in the steps below.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. You must use a rule-based trait to define the impression event for the unsegment to be triggered in real-time. Read more about how to [create rule-based traits](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
2. Apply frequency controls to the second trait. If you wish, you can add recency controls, as well. Read more about [how to apply recency and frequency controls](../segments/recency-and-frequency.md).
3. Map the segment to any number of real-time server-to-server destinations. Read on about how to add segments to [server-to-server destinations](../destinations/add-edit-segments.md).

In this scenario, once your users have accumulated more than three impressions, they will be removed from this segment and will not see this particular creative anymore.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

Keep in mind these aspects related to processing:

* For the real-time unsegment capability to work, you must map the desired segments to realtime server-to-server destinations.
* For devices connected to a device by a [device graph](profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](merge-rule-unsegment.md#device-graph-options-unsegmentation).​
* The unsegment command will be included in a batch file, that is sent to destinations every 24 hours, for multiple devices connected by the device graph. 
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md) to prompt segment evaluation in real-time. For traits that have a [!UICONTROL time-to-live (TTL)]  when the trait [!DNL TTL] is met, the device will automatically be unsegmented within 24 hours via the batch file..​ Read more about how to [Set a Trait Expiration Interval](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).​

## Important Aspects to Note - Timing {#timing-notes}

Keep in mind these aspects related to timing:

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!DNL DCS] regions. Read more about our [!DNL DCS] regions [here](../..//reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
