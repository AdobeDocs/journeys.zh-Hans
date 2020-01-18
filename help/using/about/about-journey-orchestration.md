---
title: 关于旅程安排
description: 进一步了解旅程安排
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 关于旅程安排{#concept_nd3_mqt_52b}

利用存储在事件或数据源中的情境数据构建实时安排使用案例。

旅程安排是与Experience platform集成的应用程序服务。

![](../assets/journeydiagram.png)

旅程安排允许实时安排由来自活动的情境式数据、Adobe Experience platform的信息或来自第三方API服务的数据提供支持。 如果您使用第三方系统发送消息，则可以配置自定义操作。 如果您有Adobe Campaign Standard，您将能够使用Adobe Campaign Standard的交易消息传递功能发送电子邮件、推送通 [知和SMS](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

在事件配置选项卡中，技术用 **户配置** 旅程中预期的事件。 传入事件的数据按照Adobe体验数据模型(XDM)进行标准化。 事件来自用于已验证和未验证事件（如Adobe Mobile SDK事件）的Streaming Ingestion API。

在数据源配置选项卡中，技术用 **户配置** :

* 旅程设计人员中Adobe Experience Platform中用于条件构建和个性化用途的不同字段。
* 您在旅程设计人员中利用的其他自定义数据源。 自定义数据源是旅程安排与第三方系统或服务之间通过API的连接。 您可以连接第三方系统，如忠诚度系统。 例如，第三方服务可以是天气API。

借助旅程设计人员，企 **业用户可以** 轻松拖放进入事件、添加条件并指定要执行的操作。

然后，您可以基于以下内容创建条件：

* 时间
* 来自事件有效负荷的数据
* 来自数据源的信息：实时客户档案数据源或自定义数据源

您可以使用拆分条件将旅程中的人定向到不同的方向。

使用操作活动，您随后可以通过第三方系统发送消息。 如果您有Adobe Campaign Standard，请发送实时个性化短信、推送通知或电子邮件。

由于旅程安排是多步骤的，因此您可以创建高级场景。 例如，在第一个事件和操作之后，您可以拖动其他事件。 然后，您可以添加第二个操作，放置等待活动以等待一段时间，添加拆分条件以将人推送到两个不同的路径，然后发送不同的消息。

>[!NOTE]
>
>此文档经常更新以反映产品中最近的更改。 但是，某些屏幕截图可能与产品的界面略有不同。

