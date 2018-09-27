---
description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Derived Signals
uuid: 22527e8c-01a0-4f00-a9f3-facab23ebced
index: y
internal: n
snippet: y
translate: y
---

# Derived Signals

A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.

## Derived Signals {#topic_58AB69FE2A194E05A64D0CCB1ACD7C20}

A 
<wintitle>
  derived signal
</wintitle> qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before. 
<draft-comment otherprops="merge">
  c_tb_derived_signal.xml 
</draft-comment>


<a id="section_368430C044E342FB88B0930E10751786"></a>



**Purpose of Derived Signals** 


In [!DNL Audience Manager], you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value "product = new_car" ( `http://<domain alias>/event?product=new_car`). [!DNL Audience Manager] would connect that signal to any others created with the [!UICONTROL derived signals] tool. Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal "product = new car" that user can also qualify for traits defined by the target key and value signals. 


![](assets/derived_signal_example.png) 


**Location of [!UICONTROL Derived Signals]** 


Create and manage [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** from the sidebar navigation. 

## Create a Derived Signal {#task_5F57826F8EA142C39A91F2FD2332035B}

<draft-comment otherprops="merge">
  t_tb_create_derived.xml 
</draft-comment>



**To create a [!UICONTROL derived signal]** 

1. Select **[!UICONTROL Derived Signals]** from the [!UICONTROL Tools] menu.
1. Provide a:


* *(Optional)* Integration Code
* Source Key
* Source Value
* Target Key
* Target Value


1. Click **[!UICONTROL Add Signal]**.
>[!MORE_LIKE_THIS]
>
>* [Edit a Derived Signal](derived-signals.md#task_03A867938CD54F9F9A624C630CCDEC3E)
>* [Delete a Derived Signal](derived-signals.md#task_956A182EC2A2487EB46A0EABC6768964)

## Edit a Derived Signal {#task_03A867938CD54F9F9A624C630CCDEC3E}

<draft-comment otherprops="merge">
  t_tb_edit_derived.xml 
</draft-comment>



**To edit a [!UICONTROL derived signal]** 

1. Hover over the signal, then click **[!UICONTROL Edit]**.
1. Make the required code, key, or value changes, then click **[!UICONTROL Save]**.
>[!MORE_LIKE_THIS]
>
>* [Create a Derived Signal](derived-signals.md#task_5F57826F8EA142C39A91F2FD2332035B)
>* [Delete a Derived Signal](derived-signals.md#task_956A182EC2A2487EB46A0EABC6768964)

## Delete a Derived Signal {#task_956A182EC2A2487EB46A0EABC6768964}

<draft-comment otherprops="merge">
  t_tb_delete_derived.xml 
</draft-comment>



**To delete a [!UICONTROL derived signal]** 

* Hover over the signal, then click **[!UICONTROL Delete]**.
