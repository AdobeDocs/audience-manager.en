---
description: Describes the available date ranges and how data ages out of each interval in the reports for an Addressable Audience or Destination.
seo-description: Describes the available date ranges and how data ages out of each interval in the reports for an Addressable Audience or Destination.
seo-title: Date Ranges in Addressable Audiences and Destinations
solution: Audience Manager
title: Date Ranges in Addressable Audiences and Destinations
topic: DIL API
uuid: 259c4778-05bb-4977-8659-ab46b1c7ec43
index: y
internal: n
snippet: y
translate: y
---

# Date Ranges in Addressable Audiences and Destinations


## Available Date Ranges and Time Zones {#section_854A764AEC374F5D99DC8331CACFCAAF}

Reports for your [!UICONTROL  Addressable Audiences] and [ Destinations](../../c_features/c_destinations/c_destinations.md#concept_5BDA346C376C4B719EA394108AB2735A) use the same date range intervals. The date range options include: 

* Last 1 Day (This interval runs from Midnight to Midnight of the previous 24-hour period. It is not a real- or current-time metric.)
* Last 7 Days
* Last 14 Days
* Last 30 Days
* Last 60 Days
* Last 90 Days
* Lifetime
All dates and date ranges are set in the UTC time zone. See [ Time Zones in Audience Manager](../../c_reference/aam-time-zones.md#concept_9E98F473CB1A4A81A68C68CA552D9507). 

## Data in Date Range Intervals {#section_E2A4667E701846E896E1003829C2FEDF}

The [!UICONTROL  Addressable Audience] and [!UICONTROL  Destination] metrics return a count of unique users for the selected time interval. For example, a visitor is only counted once, even if they come to your site multiple times. The first visit is the unique visit and gets recorded. The subsequent visits are returning visits and are not counted because they're not unique. 

Date ranges contain data for the selected time interval or older. And, the data ages out of each report interval as time passes. For example, let's assume you see 2 visitors after choosing the Last 30 Days option. In the reports, these visitors: 

* *Will be* included in the results returned by the longer time intervals (60-days, 90-days, and Lifetime).
* *Will not be* included in the shorter intervals that precede the Last 30 Day option (Current, 7-days, and 14-days).
And, on day 31, these visitors only show up in the 60-day, 90-day, and Lifetime results. They have aged out of the 30-day interval. Visitors do not age out of the Lifetime interval. 
