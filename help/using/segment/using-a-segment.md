---
product: adobe campaign
solution: Journey Orchestration
title: 使用区段
description: 了解如何使用细分
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---


# 在条件中使用区段 {#using-a-segment}

本节介绍如何在旅程条件中使用区段。 要了解如何在您的旅程中使用&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件，请参阅此[部分](../building-journeys/segment-qualification-events.md)。

要在旅程条件中使用区段，请执行以下步骤：

1. 打开旅程，放置&#x200B;**[!UICONTROL Condition]**&#x200B;活动，然后选择&#x200B;**数据源条件**。
   ![](../assets/journey47.png)

1. 单击&#x200B;**[!UICONTROL Add a path]**&#x200B;以获取所需的每个额外路径。 对于每个路径，单击&#x200B;**[!UICONTROL Expression]**&#x200B;字段。

   ![](../assets/segment3.png)

1. 在左侧，展开&#x200B;**[!UICONTROL Segments]**&#x200B;节点。 拖放要用于您的条件的区段。 默认情况下，段上的条件为true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >只有具有&#x200B;**已实现**&#x200B;和&#x200B;**现有**&#x200B;区段参与状态的个人才会被视为区段的成员。 有关如何评估区段的详细信息，请参阅[分段服务文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

有关旅程条件以及如何使用简单的表达式编辑器的详细信息，请参阅[条件活动](../building-journeys/condition-activity.md#about_condition)。