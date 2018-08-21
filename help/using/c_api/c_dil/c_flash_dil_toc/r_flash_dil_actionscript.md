---
description: Code for your Flash object to send Analytics data to Audience Management.
seo-description: Code for your Flash object to send Analytics data to Audience Management.
seo-title: Flash DIL ActionScript Library
solution: Audience Manager
title: Flash DIL ActionScript Library
uuid: 24f467a3-898b-4b74-93f3-dbfdc9148db8
index: y
internal: n
snippet: y
translate: y
---

# Flash DIL ActionScript Library



>>[!NOTE]
>>
>>
>>* For each Flash object, the code supports one partner instance ( ` d.partner`) only.
>>* Requires the Adobe AppMeasurement AS library version 3.5.2 or higher.

>
>
>```
>js>import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
>import com.adobe.am.DIL; 
>  
>var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
>var d:DIL = new DIL(); 
>d.partner = "<partner>";// Partner name 
>d.containerNSID = <container NSID>; // Optional, defaults to 0 
>s.loadModule(d);
>```

