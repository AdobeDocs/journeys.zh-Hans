---
product: adobe campaign
title: 使用区段
description: 了解如何使用区段
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# 在条件中使用区段 {#using-a-segment}

本节介绍如何在历程条件中使用区段。 要了解如何在历程中使用&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件，请参阅此[部分](../building-journeys/segment-qualification-events.md)。

要在历程条件中使用区段，请执行以下步骤：

1. 打开旅程，拖放&#x200B;**[!UICONTROL Condition]**&#x200B;活动并选择&#x200B;**数据源条件**。
   ![](../assets/journey47.png)

1. 对于每个需要的额外路径，单击&#x200B;**[!UICONTROL Add a path]**。 对于每个路径，单击&#x200B;**[!UICONTROL Expression]**&#x200B;字段。

   ![](../assets/segment3.png)

1. 在左侧，展开&#x200B;**[!UICONTROL Segments]**&#x200B;节点。 拖放要用于条件的区段。 默认情况下，区段上的条件为true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >只有具有&#x200B;**Remilated**&#x200B;和&#x200B;**Existing**&#x200B;区段参与状态的个人才会被视为区段的成员。 有关如何评估区段的更多信息，请参阅[Segmentation Service文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

有关历程条件以及如何使用简单表达式编辑器的更多信息，请参阅[条件活动](../building-journeys/condition-activity.md#about_condition)。
