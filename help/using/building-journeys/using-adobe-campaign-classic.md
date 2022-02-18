---
product: adobe campaign
solution: Journey Orchestration
title: 使用Adobe Campaign v7/v8操作
description: 了解Adobe Campaign v7/v8操作
feature: Journeys
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 12%

---

# 使用 Adobe Campaign v7/v8 {#using_campaign_classic}

如果您具有Adobe Campaign v7或v8，则集成可用。 它允许您使用Adobe Campaign事务型消息传送功能发送电子邮件、推送通知和短信。

Journey Orchestration 实例和 Campaign 实例之间的连接是在预配置时通过 Adobe 来设置的。联系Adobe。

要使此功能正常工作，您需要配置专用操作。 请参阅 [部分](../action/acc-action.md).

本节介绍了端到端用例 [部分](../usecase/campaign-classic-use-case.md).

1. 从事件开始设计您的历程。 请参阅 [部分](../building-journeys/journey.md).
1. 在 **操作** 选择Campaign操作并将其添加到历程中。
1. 在 **操作参数**，则会显示消息有效负载中预期的所有字段。 您需要将每个字段与要使用的字段进行映射（来自事件或来自数据源）。 这类似于自定义操作。 请参阅 [部分](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
