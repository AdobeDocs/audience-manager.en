---
description: Capture and send a referring URL to Audience Manager.
seo-description: Capture and send a referring URL to Audience Manager.
seo-title: Capture Referring URL
solution: Audience Manager
title: Capture Referring URL
uuid: 729c6137-622b-42ee-9c72-71ec528e1d46
index: y
internal: n
snippet: y
translate: y
---

# Capture Referring URL


>[!NOTE]
>
>This method works only when users move between pages with similar protocols (HTTP vs HTTPS). For example, the browser retains a referring URL when you navigate from a secure site to another secure site. Browsers do not retain the referring URL when you move between secure and unsecure sites. This behavior is normal browser functionality and cannot be circumvented by DIL.



**Code Sample** 

Your code could look similar to the following: 
```
javavar adobe_dil = DIL.create({ partner : " 
<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
```

