---
product: adobe campaign
solution: Journey Orchestration
title: 关于事件
description: 了解事件
translation-type: tm+mt
source-git-commit: 3dd7cd4dc4e4398b029dd1becd11c8dd7e7c3542
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 55%

---


# 一般原则 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="关于事件"
>abstract="事件与个人相关联。它与个人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与个人相关的某件事情有关（例如，某人达到 10 000 个忠诚点）。这就是 [!DNL Journey Orchestration] 在旅程中将侦听的内容，以编排最佳的后续行动。"

事件与个人相关联。它与个人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与个人相关的某件事情有关（例如，某人达到 10 000 个忠诚点）。这就是 [!DNL Journey Orchestration] 在旅程中将侦听的内容，以编排最佳的后续行动。

此配置是&#x200B;**强制性的**，因为 [!DNL Journey Orchestration] 设计用于侦听事件，并且始终由&#x200B;**技术用户**&#x200B;执行。

事件配置允许您定义 [!DNL Journey Orchestration] 将作为事件接收的信息。您可以使用多个事件（在旅程的不同步骤中），而多个旅程可以使用相同的事件。

如果您编辑在草稿或实时旅程中使用的事件，则只能更改名称、描述或添加有效负载字段。我们严格限制草稿或实时旅程的版本，以避免中断旅程。

您可以定义两种类型的事件:

* **基于规则** 的事件：此类型的事件不生成eventID。使用简单的表达式编辑器，您只需定义一个规则，系统将使用该规则来识别将触发您旅程的相关事件。 此规则可以基于事件有效负荷中可用的任何字段，例如用户档案的位置或添加到用户档案购物车的项目数。

   >[!CAUTION]
   >
   >为基于规则的事件定义限制规则。 它将特定组织(ORG)的旅程可处理的合格事件数限制为每秒5000。 它对应于Journey OrchestrationSLA。 请参阅此[页面](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html)。

* **系统生** 成事件：这些事件需要eventID。创建事件时会自动生成此eventID字段。 推送事件的系统不应生成ID，它应传递有效负荷预览中可用的ID。

要了解如何创建事件，请参阅此[页面](../event/about-creating.md)。

