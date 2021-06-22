---
description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Look-Alike Modeling FAQ
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
---
# Look-Alike Modeling FAQ

## Overview {#overview}

This article provides answers to the most frequently asked questions about [!UICONTROL Look-Alike Modeling].

## Questions {#questions}

**Why am I getting a flat [!UICONTROL Accuracy & Reach] graph?**

A flat [!UICONTROL Accuracy & Reach] graph means that almost every user received the same score by the model. This can happen when you include site visitor trait in the data sources that you ran the model on. To avoid this, remove the generic trait from the model input during the model creation step, by using the [!UICONTROL Exclusions] field.

&nbsp;

**Why do some of my top influential traits have very small audiences?**

The algorithm selects traits that are highly correlated with the baseline trait. For example, if a given trait has 100% overlap with the baseline trait, it will have a very high weight, even if the number of users in that trait is small.

&nbsp;

**Why has my model not run/rerun?**

Models which have produced results will continue to run only if you have created at least one active algorithmic trait and mapped it to an active segment and a destination.

&nbsp;

**Why did my model not produce any results?**

This is typically caused by not having significant trait overlaps between the baseline population and the population in the selected data sources.

&nbsp;

**Is there any recommendation on the baseline trait or segment size?**

A few thousand users should be enough to run the model on, given that there is significant trait overlap between the baseline population and the population in the selected data sources. [!UICONTROL Look-Alike Modeling] produces more accurate results, the larger the baseline is.

&nbsp;

**What third party data sources should I choose for my model?**

Use data sources which have at least some overlap with your baseline trait/segment, but at the same time bring in additional users. You should also consider the cost associated with each data feed. Cost and pricing models vary among data providers in [!UICONTROL Audience Marketplace].

&nbsp;

**Does it cost to use third party data for modeling?**

It depends on the pricing model of the selected data feed. Some feeds allow modeling at no cost, while others charge you a fee. See [Billing for Data Feed Buyers](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) for details.

&nbsp;

**How many models/traits am I allowed to create?**

Currently, you can create up to 20 algorithmic models and 50 algorithmic traits.

&nbsp;

**What is the refresh frequency of the model training and algorithmic trait population?**

The model retrains once every 8 days, along with refreshing the algorithmic trait population.
