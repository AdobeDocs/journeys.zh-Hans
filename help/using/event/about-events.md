---
product: adobe campaign
title: 关于事件
description: 了解事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# 一般原则 {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_



>[!CONTEXTUALHELP]
>id="jo_events"
>title="关于事件"
>abstract="事件与个人相关联。它与个人的行为或者与个人发生的事情有关。这就是 [!DNL Journey Orchestration] 在历程中将侦听的内容，以编排最佳的后续行动。"

事件与个人相关联。它与一个人的行为（例如，一个人购买了产品、访问了商店、退出了网站等）或与一个人相关的某件事（例如，一个人达到了 10,000 个忠诚度积分）有关。这就是 [!DNL Journey Orchestration] 在历程中将侦听的内容，以编排最佳的后续行动。

此配置是&#x200B;**强制性的**，因为 [!DNL Journey Orchestration] 设计用于侦听事件，并且始终由&#x200B;**技术用户**&#x200B;执行。

事件配置允许您定义 [!DNL Journey Orchestration] 将作为事件接收的信息。您可以使用多个事件（在历程的不同步骤中），而多个历程可以使用相同的事件。

如果您编辑在草稿或实时历程中使用的事件，则只能更改名称、描述或添加有效负载字段。我们严格限制草稿或实时历程的版本，以避免中断历程。

您可以定义两种类型的事件：

* **基于规则**&#x200B;的事件：此类型的事件不生成 eventID。使用简单表达式编辑器，您只需定义规则即可，系统将使用该规则来识别将触发历程的相关事件。此规则可以基于事件有效负荷中可用的任何字段，例如轮廓的位置或添加到轮廓购物车的项目数。

  >[!CAUTION]
  >
  >为基于规则的事件定义上限规则。它将历程可为给定组织 (ORG) 处理的合格事件数限制为每秒 5000 个。它对应于 Journey Orchestration SLA。请参阅此[页面](https://helpx.adobe.com/cn/legal/product-descriptions/journey-orchestration.html)。

* **系统生成**&#x200B;的事件：这些事件需要 eventID。创建事件时会自动生成此 eventID 字段。推送事件的系统不应生成 ID，它应传递有效负荷预览中可用的 ID。

Journey Orchestration 需要将事件流式传输或成批发送到 Adobe Experience Platform 中。此数据不一定需要转至实时轮廓。如果要在单独的历程中使用事件进行分段或查找，我们建议您为轮廓启用数据集。

要了解如何创建事件，请参阅此[页面](../event/about-creating.md)。
