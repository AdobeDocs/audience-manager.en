---
description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Derived Signals
uuid: 579a4215-acd9-4694-b6da-c20c832bd2bc
index: y
internal: n
snippet: y
translate: y
---

# Derived Signals

**Purpose of Derived Signals** 

In Audience Manager, you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value "product = new_car" ( ` http://<domain alias>/event?product=new_car`). Audience Manager would connect that signal to any others created with the derived signals tool. Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as Trait Builder rules. For example, in the illustration below, when a user action fires the signal "product = new car" that user can also qualify for traits defined by the target key and value signals. 

![](assets/derived_signal_example.png) 

**Location of Derived Signals** 

Create and manage derived signals in **[!UICONTROL  Tools > Derived Signals]** from the sidebar navigation. 
