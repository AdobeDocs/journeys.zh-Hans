---
product: adobe campaign
title: 添加条件
description: 了解如何添加条件
feature: Journeys
role: User
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 4%

---

# 添加条件 {#concept_rbg_gqt_52b}

对于系统生成的事件，您可以定义一个事件条件，以便系统过滤事件的处理。 如果条件为true，则会处理该事件。 如果条件不为true，则忽略该事件。

事件条件只能基于事件有效负载中传递的数据。 营销人员不能在画布中更改在事件级别定义的条件。 其目的是在使用此事件时强化此条件。 例如，如果您从不希望营销人员在购物车值太小时使用购物车放弃事件，则可以在“购物车值”事件字段中创建条件，并强加值超过100美元。

您可以使用简单表达式编辑器或高级表达式编辑器来设置事件条件。 请参阅[此页](../expression/expressionadvanced.md)。

例如，您可以定义一个条件，以便仅处理特定事件类型的事件并忽略其他类型。 或者，如果您的事件是购物车放弃，并且有效负荷包含购物车值字段，则您可以定义一个事件条件以仅在购物车值大于100美元时处理事件。

![](../assets/journey78.png)
