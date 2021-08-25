---
product: adobe campaign
title: 关于Adobe Experience Platform区段
description: 了解如何配置Adobe Experience Platform区段
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 8%

---

# 关于Adobe Experience Platform区段 {#about-segments}

如果您使用[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)创建区段，则可以在[!DNL Journey Orchestration]中利用这些区段。 借助专用的活动活动，您可以让个人根据Adobe Experience Platform区段入口和出口进入或前进历程。 这还允许您使用简单或高级表达式编辑器在历程中构建复杂条件。

假设您拥有“白银客户”客户细分。通过此活动，您可以使所有新的白银客户进入历程，并向其发送一系列个性化消息。您还可以轻松地基于此区段构建条件。

以下是[!DNL Journey Orchestration]为您提供的区段可能性：

* 访问Adobe Experience Platform区段列表。 请参阅[创建区段](../segment/creating-a-segment.md)。
* 在[!DNL Journey Orchestration]中直接创建区段的方法与使用Segmentation Service创建区段的方法相同。 请参阅[创建区段](../segment/creating-a-segment.md)。
* 使用简单或高级表达式编辑器在历程条件中利用区段。 请参阅[在条件中使用区段](../segment/using-a-segment.md)。
* 向历程中添加&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件，以侦听Adobe Experience Platform区段中用户档案的入口和出口。 请参阅[事件活动](../building-journeys/segment-qualification-events.md)。

## Journey Orchestration中的评价方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，受众是使用以下评估方法之一从区段定义生成的：

* 流分段 — 当新数据流入系统时，区段的受众列表会实时保持为最新。
* 批量分段 — 区段的受众列表会根据过去一小时内到达的数据，每小时更新一次。

系统根据评估区段规则的复杂性和成本来确定每个区段定义的批处理分段和流式分段之间的确定。

您可以在区段列表的&#x200B;**[!UICONTROL Evaluation method]**&#x200B;列中查看每个区段的评估方法。

首次定义区段后，用户档案会在符合条件时添加到受众。

从以前的数据回填受众最长可能需要24小时。 回填受众后，该受众会持续保持为最新状态，并始终准备进行定位。