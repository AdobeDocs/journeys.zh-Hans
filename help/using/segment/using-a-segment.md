---
product: adobe campaign
title: 在条件中使用区段
description: 了解如何使用区段
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---

# 在条件中使用区段 {#using-a-segment}

本节介绍如何在历程条件中使用区段。 要了解如何使用 **[!UICONTROL Segment qualification]** 历程中的事件，请参阅此 [部分](../building-journeys/segment-qualification-events.md).

要在历程条件中使用区段，请执行以下步骤：

1. 打开历程，放置 **[!UICONTROL Condition]** 活动并选择 **数据源条件**.
   ![](../assets/journey47.png)

1. 单击 **[!UICONTROL Add a path]** 所需的每个额外路径。 对于每个路径，单击 **[!UICONTROL Expression]** 字段。

   ![](../assets/segment3.png)

1. 在左侧，展开 **[!UICONTROL Segments]** 节点。 拖放要用于条件的区段。 默认情况下，区段的条件为true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >仅具有 **已实现** 和 **现有** 区段参与状态将被视为区段的成员。 有关如何评估区段的更多信息，请参阅 [Segmentation Service文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

有关历程条件以及如何使用简单表达式编辑器的更多信息，请参阅 [条件活动](../building-journeys/condition-activity.md#about_condition).
