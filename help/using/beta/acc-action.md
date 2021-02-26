---
product: adobe campaign
solution: Journey Orchestration
title: 关于Campaign Classic集成
description: 了解Campaign Classic集成
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 937b7235d41fe7f0395e303736974e32eea8558f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---


# 与Adobe Campaign Classic{#integrating-with-adobe-campaign-classic}集成

此集成允许您使用Adobe Campaign Classic Transactional Messaging功能发送电子邮件、推送通知和短信。

Journey Orchestration实例和Campaign Classic实例之间的连接是在预配时由Adobe设置的。

>[!CAUTION]
>
> 此集成作为私有测试版发布。 并非所有Journey Orchestration客户都能使用它。

## 重要说明

* 没有消息限制。 根据我们当前的Campaign ClassicSLA，我们将可以发送的消息数量限制为50,000/小时。 因此，历程编排只应用于单一用例(单个事件，而不是细分)。

* 您需要在画布上为每个要使用的模板配置一个操作。

* 我们建议您使用为此集成托管的专用消息中心实例，以避免影响可能正在进行的任何其他Campaign Classic操作。 营销服务器可以托管或预置。 所需的生成是21.1 Release Candiate。

* 没有验证有效负荷或Campaign Classic消息是否正确。

* 您不能对区段资格使用Campaign Classic操作。

## 先决条件

在Campaign Classic中，您需要创建并发布事务性消息及其关联事件。 请参阅[Adobe Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

联系Adobe以获取与每条消息对应的JSON有效负荷。 然后，在Journey Orchestration中配置操作时，您将粘贴此有效负荷（请参阅下文）。

以下是一个示例：

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

在Journey Orchestration中，您需要为每个事务性消息配置一个操作。 按照以下步骤操作：

1. 创建新操作。 请参阅此[部分](../action/action.md)。
1. 输入名称和说明。
1. 在&#x200B;**操作类型**&#x200B;字段中，选择&#x200B;**Adobe Campaign Classic**。
1. 单击&#x200B;**Payload**&#x200B;字段，然后粘贴与Campaign Classic消息对应的JSON有效负荷示例。 联系Adobe以获取此有效负荷。
1. 调整不同的字段。 某些字段(如渠道参数和个性化字段(ctx))需要定义为变量。
1. 单击&#x200B;**保存**。

![](../assets/accintegration1.png)

对于配置的每个操作，旅程设计器调色板中都提供一个操作活动。

## 在旅程中添加消息

1. 从事件开始，设计您的旅程。 请参阅此[部分](../building-journeys/journey.md)。
1. 在调板的&#x200B;**操作**&#x200B;部分，选择一个Campaign Classic操作并将其添加到您的旅程中。
1. 在&#x200B;**操作参数**&#x200B;中，将显示消息有效负荷中预期的所有字段。 您需要将每个字段与要使用的字段进行映射，无论是从事件还是从数据源。 这与自定义操作类似。 请参阅此[部分](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)

