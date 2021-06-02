---
product: adobe campaign
title: 关于Campaign Classic集成
description: 了解Campaign Classic集成
hide: true
hidefromtoc: true
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 2%

---

# 与 Adobe Campaign Classic 集成 {#integrating-with-adobe-campaign-classic}

此集成允许您使用Adobe Campaign Classic事务型消息传送功能发送电子邮件、推送通知和短信。

Journey Orchestration实例和Campaign Classic实例之间的连接是在预配时通过Adobe来设置的。

>[!CAUTION]
>
> 此集成作为私有测试版发布。 它并非对所有Journey Orchestration客户都可用。

## 重要说明

* 没有消息限制。 根据我们当前的Campaign ClassicSLA，我们将可发送的消息数量限制为50,000/小时。 因此，历程编排仅应用于单一用例（单个事件，而不是区段）。

* 您需要在每个要使用的模板的画布上配置一个操作。

* 我们建议您使用为此集成托管的专用消息中心实例，以避免影响您可能正在进行的任何其他Campaign Classic操作。 营销服务器可以是托管的，也可以是内部部署的。 所需的内部版本是21.1发行候选版本。

* 没有验证有效负载或Campaign Classic消息是否正确。

* 不能将Campaign Classic操作与区段鉴别结合使用。

## 先决条件

在Campaign Classic中，您需要创建并发布事务型消息及其关联事件。 请参阅[Adobe Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

联系Adobe以获取与每条消息对应的JSON有效负载。 然后，在Journey Orchestration中配置操作时，您将粘贴此有效负载（请参阅下文）。

示例如下：

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

## 配置操作

在Journey Orchestration中，您需要为每个事务型消息配置一个操作。 请执行以下步骤：

1. 创建新操作。 请参阅此[部分](../action/action.md)。
1. 输入名称和描述。
1. 在&#x200B;**Action type**&#x200B;字段中，选择&#x200B;**Adobe Campaign Classic**。
1. 单击&#x200B;**Payload**&#x200B;字段，并粘贴与Campaign Classic消息对应的JSON有效负载示例。 联系Adobe以获取此有效负载。
1. 调整不同的字段。 某些字段(如渠道参数和个性化字段(ctx))需要定义为变量。
1. 单击&#x200B;**保存**。

![](../assets/accintegration1.png)

对于配置的每个操作，历程设计器面板中都提供了一个操作活动。

## 在历程中添加消息

1. 从事件开始设计您的历程。 请参阅此[部分](../building-journeys/journey.md)。
1. 在面板的&#x200B;**Action**&#x200B;部分中，选择Campaign Classic操作并将其添加到历程中。
1. 在&#x200B;**操作参数**&#x200B;中，将显示消息有效负荷中预期的所有字段。 您需要将每个字段与要使用的字段进行映射（来自事件或来自数据源）。 这类似于自定义操作。 请参阅此[部分](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
