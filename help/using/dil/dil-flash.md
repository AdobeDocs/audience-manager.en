---
description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
---

# Flash DIL{#flash-dil}

Collect data sent from FLA files to Analytics and work with that information in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] is an [!DNL ActionScript] code library that lets you work with video playback data in Audience Manager. [!DNL Flash DIL] works by capturing SWF content the Adobe [!UICONTROL AppMeasurement] library passes in to Analytics. [!DNL Flash DIL] sends that data to the separate [!UICONTROL DIL] JavaScript data collection module, which passes that information to Audience Manager. Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals. 

## Requirements for Flash DIL Data Collection {#requirements}

General implementation and code-related requirements.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementation Requirements**

[!UICONTROL Flash] data collection requires:

* The [!UICONTROL DIL] class library ( `dil.swc`). Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact. 

* JavaScript [!UICONTROL DIL] data collection code on the page. 
* [DIL ActionScript library](../dil/dil-flash.md#flash-dil-actionscript) loaded in the Flash object you want to collect data from. 
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**Set AllowScriptAccess to `Always` or `sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] data collection will not work if `AllowScriptAccess` is set to `never`. See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Code Placement**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. When the [!DNL FLA] file loads first, before [!UICONTROL DIL] data collection is ready, you can miss the initial data signals that [!UICONTROL Flash DIL] sends to that module. However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL]. 

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] captures page view, link tracking, media tracking, and other media view events from the Adobe [!UICONTROL AppMeasurement] library.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Page View Events**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName` 
* `channel` 
* `campaign` 
* `products` 
* `events` 
* `prop1 - prop75` 
* `eVar1 - eVar75`

**Link Tracking Events**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type of track link called) 
* `pev1` (Link URL) 
* `pev2`(Link text)

**Media Tracking Events**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**Other Data Points**

Data from these parameters is collected by default:

* `mediaName` (Media/video element name) 
* `mediaAdName` (Ad name) 
* `mediaAdParentName` (Name of the primary media content the ad is nested under) 
* `mediaAdParentPod` (The pod or ad break within the primary content where the ad plays) 
* `mediaAdParentPodPos` (The numeric position within the pod where the ad plays. More than one ad can play within a pod.

>[!MORE_LIKE_THIS]
>
>* [AppMeasurement Flash, Flex, and OSMF Implementation Guide](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)

## Flash DIL Data in Audience Manager {#flash-dil-data}

The [!UICONTROL Flash DIL] module turns Adobe AppMeasurement data into Audience Manager traits and unused signals.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. Traits are key-value pairs and are used to build segments. For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**Match Audience Manager Traits to Analytics Variables**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

See the table for examples:  

|  Analytics Data Element  | Analytics Example  | As Audience Manager Trait  |
|---|---|---|
|  **prop** | `c30=foo`  | `c_prop30=foo`  |
|  **evar** | `v35=bar`  | `c_evar35=bar`  |
|  **events** | `events=event10`  | `c_events=event10`  |

**DIL/Analytics Data as Unused Signals**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library. 

>[!MORE_LIKE_THIS]
>
>* [Traits](../features/traits/trait-details-page.md)
>* [Signals, Traits, and Segments](../reference/signal-trait-segment.md)
>* [Key-Value Pairs Explained](../reference/key-value-pairs-explained.md)
>* [Prefix Requirements for Key Variables](../features/traits/trait-variable-prefixes.md)

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code for your [!DNL Flash] object to send Analytics data to Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only. 
>
>* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher. 
>

```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

