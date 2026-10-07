---
product: adobe campaign
title: 在条件中使用区段
description: 了解如何使用区段
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 27%
---
# 在条件中使用区段 {#using-a-segment}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？ 请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。 如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_


本节介绍如何在历程条件中使用区段。 要了解如何在历程中使用&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件，请参阅此[部分](../building-journeys/segment-qualification-events.md)。

要在历程条件中使用区段，请执行以下步骤：

1. 打开历程，删除&#x200B;**[!UICONTROL Condition]**&#x200B;活动并选择&#x200B;**数据Source条件**。
   ![](../assets/journey47.png)

1. 单击每个所需额外路径的&#x200B;**[!UICONTROL Add a path]**。 对于每个路径，单击&#x200B;**[!UICONTROL Expression]**&#x200B;字段。

   ![](../assets/segment3.png)

1. 在左侧，展开&#x200B;**[!UICONTROL Segments]**&#x200B;节点。 拖放要用于条件的区段。 默认情况下，区段的条件为true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >只有具有&#x200B;**已实现**&#x200B;和&#x200B;**现有**&#x200B;区段参与状态的个人才会被视为该区段的成员。 有关如何评估区段的更多信息，请参阅[分段服务文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

有关历程条件以及如何使用简单表达式编辑器的详细信息，请参阅[条件活动](../building-journeys/condition-activity.md#about_condition)。
