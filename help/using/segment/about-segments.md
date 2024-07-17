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
source-wordcount: '358'
ht-degree: 10%

---

# 关于Adobe Experience Platform区段 {#about-segments}

如果您使用[Adobe Experience Platform分段服务](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hans)创建区段，则可以在[!DNL Journey Orchestration]中利用它们。 通过专门的活动活动，您可以根据Adobe Experience Platform区段入口和出口，让个人进入历程或是在历程中前进。 这还允许您使用简单或高级表达式编辑器在历程中构建复杂条件。

假设您拥有“白银客户”客户细分。通过此活动，您可以使所有新的白银客户进入历程，并向他们发送一系列个性化消息。 您还可以基于此区段轻松构建条件。

以下是[!DNL Journey Orchestration]可为您提供区段的可能性：

* 访问Adobe Experience Platform区段的列表。 请参阅[创建区段](../segment/creating-a-segment.md)。
* 直接在[!DNL Journey Orchestration]中创建区段，其方式与使用分段服务创建区段的方式相同。 请参阅[创建区段](../segment/creating-a-segment.md)。
* 使用简单或高级表达式编辑器在历程的条件下利用区段。 请参阅[在条件](../segment/using-a-segment.md)中使用区段。
* 将&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件添加到您的历程，以侦听Adobe Experience Platform区段中用户档案的进出口。 查看[事件活动](../building-journeys/segment-qualification-events.md)。

## Journey Orchestration中的评估方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，使用下列评估方法之一从区段定义生成受众：

* 流式分段 — 当新数据流入系统时，区段的受众列表会实时保持最新。
* 批量分段 — 区段的受众列表会根据过去一小时内到达的数据每小时更新一次。

系统根据分段规则的复杂性和评估成本，对每个分段定义进行批量分段和流式分段之间的确定。

您可以在区段列表的&#x200B;**[!UICONTROL Evaluation method]**&#x200B;列中查看每个区段的评估方法。

首次定义区段后，用户档案将在符合条件时添加到受众。

从先前数据回填受众最多可能需要 24 小时。回填受众后，受众会持续保持最新状态，并始终准备好用于定位。