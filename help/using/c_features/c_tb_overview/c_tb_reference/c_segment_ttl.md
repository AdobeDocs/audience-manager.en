---
description: How trait time-to-live (TTL) interval affects segment membership.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment Time to Live Explained
solution: Audience Manager
title: Segment Time to Live Explained
uuid: 540427f3-1882-41c9-b31b-840be365712d
index: y
internal: n
snippet: y
translate: y
---

# Segment Time to Live Explained

**Time to Live** 

TTL defines how long a site visitor remains in a segment after the last trait qualification event. TTL is set on traits and not on segments. Visitors fall out of a segment if they do not see a qualifying trait before the end of the TTL interval. The default TTL for new traits is 120-days. When set to 0-days, the trait never expires. [ Set the TTL value](../../../c_features/c_tb_overview/c_tb_main/c_trait_create/c_tb_rules_traits/t_tb_ttl.md#task_F17639E26C2744A0942461FCCD4D4DC7) when you create or edit a trait in the Advanced Options section of the trait creation interface. 

**TTL and Dropping Out of a Segment** 

A user falls out of a segment if they do not see any of its traits within the TTL interval. For example, if you have a 1-trait segment with a 30-day TTL, the user will drop out of that segment if they do not see the trait again within the 30 days. 

![](assets/ttl_1.png) 

**TTL and Segment Renewal** 

The TTL resets, and the user remains in a segment, if they see that segment’s trait within the TTL period. Also, because most segments contain multiple traits with their own TTL periods, a user can remain in a segment (and reset the TTL interval) as long as they keep seeing any traits associated with a segment. For example, say you have Segment 1 composed of Trait A (30-day TTL) and Trait B (15-day TTL). Assuming the user sees each trait only once, the illustration below outlines the TTL renewal process and total in-segment duration. 

![](assets/ttl_2.png) 

**Audience Manager TTLs are Independent of Third-Party TTL Settings** 

Remember, the TTL set on your Audience Manager pixel operates independently from the TTL set on other pixels used by third parties (DSPs, ad networks, etc.). 
>[!MORE_LIKE_THIS]
>
>* [ Set a Trait Expiration Interval ](t_tb_ttl.md#task_F17639E26C2744A0942461FCCD4D4DC7)
