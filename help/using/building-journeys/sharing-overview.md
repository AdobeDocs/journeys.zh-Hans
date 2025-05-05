---
product: adobe campaign
title: 历程步骤共享概述
description: 历程步骤共享概述
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 3%

---

# 历程步骤共享概述{#sharing-overview}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


[!DNL Journey Orchestration]自动将旅程性能数据发送到Adobe Experience Platform，以便与其他数据结合进行分析。

>[!NOTE]
>
>默认情况下，历程步骤事件的所有实例都会激活此功能。 您无法修改或更新在预配步骤事件期间创建的架构和数据集。 默认情况下，这些架构和数据集处于只读模式。

例如，您已设置发送多封电子邮件的历程。 此功能允许您将[!DNL Journey Orchestration]数据与下游事件数据相结合，如发生了多少转化、网站上发生了多少参与或存储中发生了多少事务。 旅程信息可与Adobe Experience Platform上的其他数字资产或离线资产中的数据相结合，以更全面地查看性能。

[!DNL Journey Orchestration]会自动创建必要的架构，并针对个人在历程中执行的每个步骤，将数据集流式传输到Adobe Experience Platform。 步骤事件对应于在历程中从某个节点移动到另一个节点的个人。 例如，在包含事件、条件和操作的历程中，会将三个步骤事件发送到Adobe Experience Platform。

传递的XDM字段列表是全面的。 有些包含系统生成的代码，而其他则具有易于用户识别的友好名称。 示例包括历程活动的标签或步骤状态：操作超时或出错的次数。

>[!CAUTION]
>
>无法为实时配置文件服务打开数据集。 请确保已关闭&#x200B;**[!UICONTROL Profile]**&#x200B;切换开关。

历程会在发生数据时以流式方式发送数据。 您可以使用查询服务查询此数据。 您可以连接到Customer Journey Analytics或其他BI工具，以查看与这些步骤相关的数据。

将创建以下架构：

* [!DNL Journey Orchestration]的历程步骤事件架构 — 与历程元数据绑定的历程步骤事件。
* 具有[!DNL Journey Orchestration]的历程字段的历程架构 — 描述历程的历程元数据。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

传递以下数据集：

* 历程步骤事件
* 历程

![](../assets/sharing3.png)

此处详细列出了传递到Adobe Experience Platform的XDM字段列表：

* [步骤事件字段列表](../building-journeys/sharing-field-list.md)
* [旧版步骤事件字段](../building-journeys/sharing-legacy-fields.md)


## 与客户历程分析集成{#integration-cja}

Journey Orchestration步骤事件可以链接到[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)中的其他数据集。 以下是常规工作流程：

* Customer Journey Analytics摄取“历程步骤事件”数据集。
* 关联的“Journey Orchestration的历程步骤事件架构”中的&#x200B;**profileID**&#x200B;字段被定义为标识字段。 在Customer Journey Analytics中，您可以将此数据集链接到与基于人员的标识符具有相同值的任何其他数据集。
* 如果要在Customer Journey Analytics中使用此数据集，请参阅此[文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=zh-Hans)以进行跨渠道历程分析。
