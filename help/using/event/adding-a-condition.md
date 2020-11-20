---
product: adobe campaign
solution: Journey Orchestration
title: 添加条件
description: 了解如何添加条件
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 4%

---



# 添加条件 {#concept_rbg_gqt_52b}

事件条件允许系统过滤事件的处理。 如果条件为true，则处理事件。 如果条件不为true，则忽略事件。

事件条件只能基于事件有效负荷中传递的数据。 营销人员不能在画布中更改在事件级别定义的条件。 其目的是在使用此事件时加强此条件。 例如，如果您不希望营销人员在购物车价值太小时使用购物车放弃事件，您可以在“购物车价值”事件字段上创建一个条件，并强加一个超过100美元的值。

您可以使用简单的表达式编辑器或高级表达式编辑器设置事件条件。 请参阅[此页](../expression/expressionadvanced.md)。

例如，您可以定义一个条件，以仅处理特定事件的事件类型并忽略其他类型。 或者，如果事件是购物车放弃，而有效负荷包括购物车值字段，则您可以定义一个事件条件，以便仅在购物车值大于100美元时处理事件。

![](../assets/journey78.png)
