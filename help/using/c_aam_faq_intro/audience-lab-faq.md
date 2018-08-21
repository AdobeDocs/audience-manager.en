---
description: Frequently asked questions about the Audience Lab feature.
seo-description: Frequently asked questions about the Audience Lab feature.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Audience Lab FAQ
topic: DIL API
uuid: 24ac421a-edc3-4d0b-af45-2da78562e519
index: y
internal: n
snippet: y
translate: y
---

# Audience Lab FAQ

**Do the test segments created in the test groups have different segment IDs? How do I map the IDs to different destinations?** 

Yes, the test segments have different segment IDs. For destinations with Auto-fill Destination Mapping or segments sent to Google, [!UICONTROL  Audience Lab] will handle the mapping values just like the destinations normally would. 

**Can the same conversion trait be associated with multiple test groups?** 

Yes, this is allowed. Think of a case of one test using a male segment associated to conversion X and one test using a female segment associated to conversion X. It doesn't matter that both tests are driving conversions since they are testing two different audiences. 

**Let's say a test group is using an authenticated profile for the test segment split. The authenticated profile is linked to 4 [ Audience Manager UUIDs](../c_reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8). When the visitor exhibits a conversion trait from one of the four UUIDs, does Audience Lab count this as one or four conversions?** 

In this case, Audience Lab only counts one conversion. 

**What if the visitor from the case above first exhibits the conversion trait from one of the four UUIDs linked to their authenticated profile and then also exhibits the conversion trait from two other UUIDs linked to the authenticated profile? Does this case count as one or three conversions?** 

In this case, [!UICONTROL  Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait. 

**Can a user have Segment: Read-Only access, yet also Audience Lab test segment creation access?** 

See [ Create Segment Test Groups](../c_features/audience-lab/create-test-group.md#task_B62EF6D2992941FAAEA84BE2EA11A55E) for information on how to use [!UICONTROL  Audience Lab] with RBAC privileges. 

**Can I use Audience Lab in conjunction with the Profile Link Device Graph and External Device Graphs ([ Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph)?** 

For now, Audience Lab can only split out segment populations by the devices connected to a qualifying device, when using the Profile Link Device Graph. We are working on adding support in Audience Lab for the other device graphs and will let you know when we do so. 
