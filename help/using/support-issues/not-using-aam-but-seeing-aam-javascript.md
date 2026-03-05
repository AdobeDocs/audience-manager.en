---
description: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
---
# We are not an Audience Manager customer, but see the Audience Manager Javascript calls on our site

## Question

We are not using Adobe Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger.

Why is this happening?

## Answer

It is likely you are running the [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) on your property. If you are, having this Audience Manager reference does not necessarily refer to the property running Audience Manager. Instead, it means that Audience Manager is powering this service.

The Audience Manager server call is usually made to [synchronize customer IDs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html).
