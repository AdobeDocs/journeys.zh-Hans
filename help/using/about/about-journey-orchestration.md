---
product: adobe campaign
solution: Journey Orchestration
title: 关于 Journey Orchestration
description: 详细了解 Journey Orchestration
feature: 历程
role: 商业从业者
level: 初学者
translation-type: ht
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---


# 关于 [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

利用存储在事件或数据源中的情境数据构建实时编排用例。

[!DNL Journey Orchestration] 是与 Adobe Experience Platform 集成的应用程序服务。

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] 允许由事件的情境数据、Adobe Experience Platform 信息或第三方 API 服务数据提供支持的实时编排。如果您使用第三方系统发送消息，则可以配置自定义操作。如果您拥有 Adobe Campaign Standard，则可以使用 Adobe Campaign Standard 的[事务性消息传送功能](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)发送电子邮件、推送通知和短信。

在事件配置选项卡中，**技术用户**&#x200B;配置历程中预期的事件。传入事件的数据按照 Adobe 体验数据模型 (XDM) 进行标准化。事件来自已验证和未验证事件（如 Adobe Mobile SDK 事件）的流摄取 API。

在数据源配置选项卡中，**技术用户**&#x200B;配置：

* 历程设计器中从 Adobe Experience Platform 公开的不同字段用于条件构建和个性化。
* 您在历程设计器中利用的其他自定义数据源。自定义数据源是指通过 API 在 [!DNL Journey Orchestration] 与第三方系统或服务之间建立的连接。您可以连接第三方系统，如忠诚度系统。例如，第三方服务可以是天气 API。

借助历程设计器，**企业用户**&#x200B;可以轻松拖放登入事件、添加条件并指定要执行的操作。

然后，根据以下数据创建条件：

* 时间
* 来自事件有效负载的数据
* 来自数据源的信息：实时客户档案数据源或自定义数据源

您可以使用拆分条件将历程中的人定向到不同的方向。

使用操作活动，您随后可以通过第三方系统发送消息。如果您有 Adobe Campaign Standard，请发送实时个性化短信、推送通知或电子邮件。

由于 [!DNL Journey Orchestration] 是多步操作，您可以创建高级方案。例如，在执行第一个事件和操作后，可以拖动其他事件。然后，您可以添加第二个操作，放置等待活动以等待一段时间，添加拆分条件以将人推送到两个不同的路径，然后发送不同的消息。

>[!NOTE]
>
>此文档经常更新以反映产品中的最新更改。但是，某些屏幕截图可能与产品的界面略有不同。
