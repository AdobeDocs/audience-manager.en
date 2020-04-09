---
description: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
---

# We are not an Audience Manager customer, but see the Audience Manager Javascript calls on our site

## Question

We are not using Adobe Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger.  Why would this be happening?

## Answer

It is likely you are running the Visitor ID service on your property. If you are, having this AAM reference does not necessarily refer to the property running Audience Manager but it means that Audience Manager is in fact powering this service. 

Please note that the AAM call is usually made to sync Set customer IDs.
