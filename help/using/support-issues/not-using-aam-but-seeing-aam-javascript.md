---
description: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
---

# We are not an Audience Manager customer, but see the Audience Manager Javascript calls on our site

## Question

We are not using Adobe Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger.

Why is this happening?

## Answer

It is likely you are running the [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) on your property. If you are, having this Audience Manager reference does not necessarily refer to the property running Audience Manager. Instead, it means that Audience Manager is powering this service.

The Audience Manager server call is usually made to [synchronize customer IDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html).
