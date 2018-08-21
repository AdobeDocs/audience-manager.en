---
description: General implementation and code-related requirements.
seo-description: General implementation and code-related requirements.
seo-title: Requirements for Flash DIL Data Collection
solution: Audience Manager
title: Requirements for Flash DIL Data Collection
uuid: 7742ed9f-1435-4784-8854-6d4830f9b026
index: y
internal: n
snippet: y
translate: y
---

# Requirements for Flash DIL Data Collection

**Implementation Requirements** 

Flash data collection requires: 
* The DIL class library ( ` dil.swc`). Obtain the DIL class library from your Partner Solutions contact.
* JavaScript DIL data collection code on the page.
* [ DIL ActionScript library](../../../c_api/c_dil/c_flash_dil_toc/r_flash_dil_actionscript.md#reference_601A61BDC2A946048AD308ECFDF7F1F5) loaded in the Flash object you want to collect data from.
* Adobe AppMeasurement AS library (version 3.5.2, or later) loaded the Flash object you want to collect data from.


**Set AllowScriptAccess to ` Always` or ` sameDomain`** 

The ` AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a Flash DIL data integration, make sure the Flash ` AllowScriptAccess` parameter is set to ` always` or ` sameDomain`. Flash DIL data collection will not work if ` AllowScriptAccess` is set to ` never`. See [ Control Access to Scripts or Host Web Page](http://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html). 

**JS DIL Code Placement** 

Try to place the JS DIL data collection module on the page so it loads before the FLA file. When the FLA file loads first, before DIL data collection is ready, you can miss the initial data signals that Flash DIL sends to that module. However, once instantiated, the DIL data collection module will capture all subsequent SWF file data passed in by Flash DIL. 
