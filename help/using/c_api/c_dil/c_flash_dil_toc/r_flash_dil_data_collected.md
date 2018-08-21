---
description: Flash DIL captures page view, link tracking, media tracking, and other media view events from the Adobe AppMeasurement library.
seo-description: Flash DIL captures page view, link tracking, media tracking, and other media view events from the Adobe AppMeasurement library.
seo-title: Data Collected by Flash DIL
solution: Audience Manager
title: Data Collected by Flash DIL
uuid: 75b7f1c9-0913-46c4-b6ba-4bdc0870cc76
index: y
internal: n
snippet: y
translate: y
---

# Data Collected by Flash DIL


>**Page View Events** 

>Unless specified otherwise by ` s.trackVars`, Flash DIL collects the following data from Adobe AppMeasurement: 
>
>* ` pageName`
>* ` channel`
>* ` campaign`
>* ` products`
>* ` events`
>* ` prop1 - prop75`
>* ` eVar1 - eVar75`
>**Link Tracking Events** 

>Unless specified otherwise by ` s.linkTrackVars`, Flash DIL collects the following data from Adobe AppMeasurement: >
>* ` pe` (Type of track link called)
>* ` pev1` (Link URL)
>* ` pev2`(Link text)


>**Media Tracking Events** 

>Unless specified otherwise by ` s.Media.trackVars`, Flash DIL collects all the data enumerated in the Page View Events section. 

>**Other Data Points** 

>Data from these parameters is collected by default: 
>
>* ` mediaName` (Media/video element name)
>* ` mediaAdName` (Ad name)
>* ` mediaAdParentName` (Name of the primary media content the ad is nested under)
>* ` mediaAdParentPod` (The pod or ad break within the primary content where the ad plays)
>* ` mediaAdParentPodPos` (The numeric position within the pod where the ad plays. More than one ad can play within a pod.
>[!MORE_LIKE_THIS]
>
>* [  ](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)
