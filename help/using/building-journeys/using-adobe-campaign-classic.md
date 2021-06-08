---
product: adobe campaign
solution: Journey Orchestration
title: 使用Adobe Campaign v7/v8操作
description: 了解Adobe Campaign v7/v8操作
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b2439788ef547b401dea64faf46d4398b9a1a0c7
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# 使用Adobe Campaign v7/v8 {#using_campaign_classic}

如果您具有Adobe Campaign v7或v8，则集成可用。 它允许您使用Adobe Campaign事务型消息传送功能发送电子邮件、推送通知和短信。

Journey Orchestration实例和Campaign实例之间的连接是在预配时Adobe设置的。 联系Adobe。

要使此功能正常工作，您需要配置专用操作。 请参阅此[部分](../action/acc-action.md)。

此[部分](../usecase/campaign-classic-use-case.md)中提供了端到端用例。

1. 从事件开始设计您的历程。 请参阅此[部分](../building-journeys/journey.md)。
1. 在面板的&#x200B;**Action**&#x200B;部分中，选择Campaign操作并将其添加到历程中。
1. 在&#x200B;**操作参数**&#x200B;中，将显示消息有效负荷中预期的所有字段。 您需要将每个字段与要使用的字段进行映射（来自事件或来自数据源）。 这类似于自定义操作。 请参阅此[部分](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
