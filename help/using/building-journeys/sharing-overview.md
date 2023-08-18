---
product: adobe campaign
title: 历程步骤共享概述
description: 历程步骤共享概述
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 8%

---

# 历程步骤共享概述{#sharing-overview}

[!DNL Journey Orchestration] 自动将旅程性能数据发送到Adobe Experience Platform，以使其可与其他数据结合进行分析。

>[!NOTE]
>
>默认情况下，历程步骤事件的所有实例都会激活此功能。 您无法修改或更新在预配步骤事件期间创建的架构和数据集。 默认情况下，这些架构和数据集处于只读模式。

例如，您已设置发送多封电子邮件的历程。 此功能允许您合并 [!DNL Journey Orchestration] 包含下游事件数据的数据，例如发生了多少转化、网站上发生了多少参与或存储中发生了多少交易。 旅程信息可与Adobe Experience Platform上的其他数字资产或离线资产中的数据相结合，以更全面地查看性能。

[!DNL Journey Orchestration] 对于个人在旅程中执行的每个步骤，自动创建必要的架构并流入到Adobe Experience Platform的数据集中。 步骤事件对应于在历程中从某个节点移动到另一个节点的个人。 例如，在包含事件、条件和操作的历程中，会将三个步骤事件发送到Adobe Experience Platform。

传递的XDM字段列表是全面的。 有些包含系统生成的代码，而其他则具有易于用户识别的友好名称。 示例包括历程活动的标签或步骤状态：操作超时或出错的次数。

>[!CAUTION]
>
>无法为实时配置文件服务打开数据集。 请确保 **[!UICONTROL Profile]** 切换已关闭。

历程会在发生数据时以流式方式发送数据。 您可以使用查询服务查询此数据。 您可以连接到Customer Journey Analytics或其他BI工具，以查看与这些步骤相关的数据。

将创建以下架构：

* 的历程步骤事件架构 [!DNL Journey Orchestration]  — 绑定到历程元数据的历程步骤事件。
* 具有历程字段的历程架构 [!DNL Journey Orchestration]  — 用于描述历程的历程元数据。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

传递以下数据集：

* 历程步骤事件
* 历程

![](../assets/sharing3.png)

此处详细列出了传递到Adobe Experience Platform的XDM字段列表：

* [步骤事件字段列表](../building-journeys/sharing-field-list.md)
* [旧版步骤事件字段](../building-journeys/sharing-legacy-fields.md)

有关向Adobe Experience Platform报告事件的步骤的更多信息，请观看此视频 [教程视频](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).

## 与客户历程分析集成{#integration-cja}

Journey Orchestration步骤事件可以链接到中的其他数据集 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans). 以下是常规工作流程：

* Customer Journey Analytics摄取“历程步骤事件”数据集。
* 此 **profileId** 关联的“用于Journey Orchestration的历程步骤事件架构”中的字段定义为标识字段。 在Customer Journey Analytics中，您可以将此数据集链接到与基于人员的标识符具有相同值的任何其他数据集。
* 如果要在Customer Journey Analytics中使用此数据集，请参阅此 [文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
