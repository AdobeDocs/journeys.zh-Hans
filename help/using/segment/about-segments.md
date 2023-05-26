---
product: adobe campaign
title: 关于 Adobe Experience Platform 区段
description: 了解如何配置Adobe Experience Platform区段
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 10%

---

# 关于 Adobe Experience Platform 区段 {#about-segments}

如果您使用 [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) 要创建区段，您可以在 [!DNL Journey Orchestration]. 通过专门的活动活动，您可以根据Adobe Experience Platform区段入口和出口，使个人进入历程或在其间前进。 这还允许您使用简单或高级表达式编辑器在历程中构建复杂条件。

假设您拥有“白银客户”客户细分。通过此活动，您可以使所有新的白银客户进入历程，并向其发送一系列个性化消息。您还可以基于此区段轻松构建条件。

以下是各种可能性 [!DNL Journey Orchestration] 为您提供区段：

* 访问Adobe Experience Platform区段的列表。 参见 [创建区段](../segment/creating-a-segment.md).
* 直接在中创建区段 [!DNL Journey Orchestration] 与使用Segmentation Service创建区段的方式相同。 参见 [创建区段](../segment/creating-a-segment.md).
* 使用简单或高级表达式编辑器在历程的条件下利用区段。 参见 [在条件中使用区段](../segment/using-a-segment.md).
* 添加 **[!UICONTROL Segment qualification]** 历程的事件，用于侦听Adobe Experience Platform区段中用户档案的进出口。 参见 [事件活动](../building-journeys/segment-qualification-events.md).

## Journey Orchestration中的评估方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，受众使用以下评估方法之一从区段定义生成：

* 流式分段 — 当新数据流入系统时，分段的受众列表会实时保持最新。
* 批量分段 — 区段的受众列表会根据过去一小时内到达的数据每小时更新一次。

系统根据分段规则的复杂性和评估成本，对每个分段定义进行批量分段和流式分段的确定。

您可以在中查看每个区段的评估方法 **[!UICONTROL Evaluation method]** 段列表的列。

首次定义区段后，用户档案会在符合条件时添加到受众。

从先前数据回填受众最多可能需要24小时。 回填受众后，受众会持续保持最新状态，并始终准备好进行定位。