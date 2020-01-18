---
title: 添加条件
description: 了解如何添加条件
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5df2fecc56d2d2d081d952f17aadf103f2f0140a

---



# 添加条件 {#concept_rbg_gqt_52b}

事件条件允许系统过滤事件的处理。 如果条件为true，则处理事件。 如果条件不为true，则忽略该事件。

事件条件只能基于事件有效负荷中传递的数据。 营销人员不能在画布中更改在活动级别定义的条件。 其目的是在使用此事件时加强此条件。 例如，如果您不希望营销人员在购物车值太小时使用购物车放弃事件，您可以在“购物车值”事件字段中创建一个条件并强加一个超过100美元的值。

您可以使用简单的表达式编辑器或高级表达式编辑器设置事件的条件。 请参见 [](../expression/expressionadvanced.md)。

例如，您可以定义一个条件，以便仅处理特定事件类型的事件并忽略其他类型。 或者，如果您的事件是购物车放弃，而有效负荷包括购物车值字段，则您可以定义一个事件条件，以便仅在购物车值大于100美元时处理该事件。

![](../assets/journey78.png)
