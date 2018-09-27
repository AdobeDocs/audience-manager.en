---
description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Name Requirements for Key Variables
uuid: d645dcdc-63b3-40ba-8797-124c440fe9c3
index: y
internal: n
snippet: y
translate: y
---

# Name Requirements for Key Variables

This article describes the naming conventions used by the key variable in a key-value pair.



**Naming Requirements for Keys** 


In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits. 

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.
* Invalid key names: `123`, `price!123`.




**Prefixing Key Variables with c_** 


The `c_` prefix is *always* required if the parameters that send in data on an event call URL use that syntax. 
