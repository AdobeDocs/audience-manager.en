---
description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Name Requirements for Key Variables
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---
# Name Requirements for Key Variables {#name-requirements-for-key-variables}

This article describes the naming conventions used by the key variable in a key-value pair.

## Naming Requirements for Keys

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits.

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.

* Invalid key names: `123`, `price!123`.

## Prefixing Key Variables with `c_`

The `c_` prefix is *always* required if the parameters that send in data on an event call URL use that syntax.
