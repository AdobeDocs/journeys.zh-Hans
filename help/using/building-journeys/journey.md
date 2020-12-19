---
product: adobe campaign
solution: Journey Orchestration
title: 关于旅程构建
description: 作为企业用户，了解如何结合事件、编排和行为活动来构建历程。
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---


# 创建旅程 {#concept_gq5_sqt_52b}

此步骤由&#x200B;**业务用户**&#x200B;执行。 这是您创造旅程的地方。 结合不同的事件、编排和操作活动，构建多步跨渠道方案。

旅程界面允许您将活动从调色板轻松拖放到画布中。 您还可以多次单击某个活动，在下一个可用步骤将其添加到画布中。 每个活动都具有特定的角色和位置。 活动被排序。 完成活动后，流将继续并处理下一个活动，依此类推。

每个旅程只允许一个命名空间。 当您删除第一个事件时，具有不同命名空间的事件将灰显。 如果第一个事件没有命名空间，则具有命名空间的所有事件都将灰显。 请参阅[此页](../event/selecting-the-namespace.md)。此外，如果旅程包含没有Adobe Experience Platform的事件，则命名空间字段组将灰显。 最后，如果您在同一旅程中使用多个事件，他们需要使用相同的命名空间。

## 快速开始{#creating_journey}

以下是创建和发布旅程的主要步骤。

1. 在顶部菜单中，单击 **[!UICONTROL Home]**&#x200B;选项卡。

   将显示旅程列表。 有关该接口的详细信息，请参阅[此页](../building-journeys/using-the-journey-designer.md)。

   ![](../assets/journey30.png)

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以创建新旅程。

   ![](../assets/journey31.png)

1. 编辑右侧显示的配置窗格中的旅程属性。请参阅[此页](../building-journeys/changing-properties.md)。

   ![](../assets/journey32.png)

1. 开始，方法是将事件活动从调色板拖放到画布中。 您还可以多次单击活动，将其添加到画布。

   ![](../assets/journey33.png)

1. 拖放其他活动并进行配置。 请参阅页面[事件活动](../building-journeys/event-activities.md)、[关于业务流程活动](../building-journeys/about-orchestration-activities.md)和[关于操作活动](../building-journeys/about-action-activities.md)。

   ![](../assets/journey34.png)

1. 您的旅程将自动保存。 测试旅程并发布。 请参阅[测试旅程](../building-journeys/testing-the-journey.md)和[发布旅程](../building-journeys/publishing-the-journey.md)。

   ![](../assets/journey36.png)

## 结束旅程{#ending_a_journey}

结束旅程有两种方式：

* 那人到达了一条路的最后活动。 最后一个活动可以是结束活动或其他活动。 没有义务用结束活动结束路径。 请参阅[此页](../building-journeys/end-activity.md)。
* 该人到达条件活动(或具有条件的等待活动)，且与任何条件不匹配。

如果允许重新进入，则人员可以重新进入旅程。 请参阅[此页](../building-journeys/changing-properties.md)。
