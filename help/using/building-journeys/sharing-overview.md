---
product: adobe campaign
title: 历程步骤共享概述
description: 历程步骤共享概述
feature: 历程
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# 历程步骤共享概述{#sharing-overview}

[!DNL Journey Orchestration] 自动将旅程性能数据发送到Adobe Experience Platform，以便与其他数据结合进行分析。

>[!NOTE]
>
>默认情况下，在历程步骤事件的所有实例上都会激活此功能。 对于历程用户档案步骤事件，将应请求激活。 不得更改在配置此功能期间创建的架构和数据集。

例如，您已设置发送多个电子邮件的历程。 此功能允许您将[!DNL Journey Orchestration]数据与下游事件数据合并，例如发生转化次数、网站上发生的参与次数或存储中发生的交易次数。 历程信息可以与Adobe Experience Platform上的数据（来自其他数字属性或来自离线属性）结合使用，以更全面地了解性能。

[!DNL Journey Orchestration] 会为个人在历程中执行的每个步骤自动将必要的架构和流创建到Adobe Experience Platform数据集。步骤事件对应于在历程中从一个节点移动到另一个节点的个人。 例如，在包含事件、条件和操作的历程中，将三步事件发送到Adobe Experience Platform。

传递的XDM字段列表非常完整。 有些代码包含系统生成的代码，而另一些代码则具有人类可读的友好名称。 示例包括历程活动的标签或步骤状态：操作超时或以错误结束的次数。

>[!CAUTION]
>
>无法为实时配置文件服务打开数据集。 请确保&#x200B;**[!UICONTROL Profile]**&#x200B;切换开关处于关闭状态。

历程在发生数据时以流方式发送数据。 您可以使用查询服务查询此数据。 您可以连接到Customer Journey Analytics或其他BI工具以查看与这些步骤相关的数据。

创建了以下架构：

* [!DNL Journey Orchestration]的历程步骤配置文件事件架构 — 体验事件，用于了解在历程中采取的步骤以及用于映射到单个历程参与者的身份映射。
* [!DNL Journey Orchestration]的历程步骤事件架构 — 与历程元数据绑定的历程步骤事件。
* 具有[!DNL Journey Orchestration]历程字段的历程架构 — 用于描述历程的历程元数据。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

传递了以下数据集：

* 历程步骤[!DNL Journey Orchestration]的配置文件事件架构
* 历程步骤事件
* 历程

![](../assets/sharing3.png)

下面详细介绍了传递到Adobe Experience Platform的XDM字段列表：

* [journeySteps 事件常用字段](../building-journeys/sharing-common-fields.md)
* [journeyStep 事件操作执行字段](../building-journeys/sharing-execution-fields.md)
* [journeyStep 事件数据提取字段](../building-journeys/sharing-fetch-fields.md)
* [journeyStep 事件身份字段](../building-journeys/sharing-identity-fields.md)
* [历程字段](../building-journeys/sharing-journey-fields.md)

有关向Adobe Experience Platform报告步骤事件的更多信息，请观看此[教程视频](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。
