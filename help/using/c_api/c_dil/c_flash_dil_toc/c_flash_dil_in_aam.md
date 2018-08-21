---
description: The Flash DIL module turns Adobe AppMeasurement data into Audience Management traits and unused signals.
seo-description: The Flash DIL module turns Adobe AppMeasurement data into Audience Management traits and unused signals.
seo-title: Flash DIL Data in Audience Manager
solution: Audience Manager
title: Flash DIL Data in Audience Manager
uuid: de13380b-2d92-4723-b4a8-4216ce1c4507
index: y
internal: n
snippet: y
translate: y
---

# Flash DIL Data in Audience Manager

Analytics Props, eVars, and events work like traits in Audience Management. Traits are key-value pairs and are used to build segments. For example, in an Analytics prop like ` prop35=foo`, ` prop35` is the key (a constant) and ` foo` is the value (a variable). 

**Match Audience Manager Traits to Analytics Variables** 

To use the Analytics data passed by Flash DIL, you should create Audience Manager traits that have: 
* The same names as their Analytics equivalents.
* A key value prefixed with ` c_`.


See the table for examples: 

|  Analytics Data Element  | Analytics Example  | As Audience Manager Trait  |
|---|---|---|
| **prop** | ` c30=foo` | ` c_prop35=foo` |
| **evar** | ` v35=bar` | ` c_evar=bar` |
| **events** | ` events=event10` | ` c_events=event10` |

**Flash DIL/Analytics Data as Unused Signals** 

Audience Manager accepts Analytics Props, eVars, and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [ Unused Signals report](../../../c_features/c_analytics/c_dynamic_reports/c_unused_signals.md#concept_D3A6A3AD84AE47589699A13A8F971BE0) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the Flash DIL library. 
>[!MORE_LIKE_THIS]
>
>* [ Traits ](c_tb_overview.md#concept_422CE72B2125457B8C2954BF06102332)
>* [ Signals, Traits, and Segments ](c_signal_trait_segment.md#concept_7550A48FE3F1415FACF0E077CFAB155F)
>* [ Key-Value Pairs Explained ](c_key_value_explained.md#concept_E4236E003076483AA939791FE2492B49)
>* [ Prefix Requirements for Key Variables ](r_tb_variable_prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC)
