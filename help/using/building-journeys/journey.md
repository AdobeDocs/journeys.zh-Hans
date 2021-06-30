---
product: adobe campaign
title: 关于历程构建
description: 作为企业用户，了解如何结合事件、编排和行为活动来构建历程。
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 784c91054e0f6b9ea12aa4b7f4079f7c2da8f949
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 12%

---

# 创建历程 {#concept_gq5_sqt_52b}

此步骤由&#x200B;**业务用户**&#x200B;执行。 您可以在此处创建历程。 结合不同的事件、编排和操作活动，构建多步跨渠道方案。

历程界面允许您轻松地将活动从面板拖放到画布中。 您还可以在下一步中双击某个活动，将其添加到画布中。 每个活动都具有特定的角色和在流程中的位置。 活动已排序。 活动完成后，该流程将继续并处理下一个活动，等等。

每个历程只允许一个命名空间。 放置第一个事件时，具有不同命名空间的事件将灰显。 如果第一个事件没有命名空间，则具有命名空间的所有事件都将灰显。 请参阅[此页](../event/selecting-the-namespace.md)。此外，如果历程包含的事件没有命名空间，则Adobe Experience Platform字段组将灰显。 最后，如果您在同一历程中使用多个事件，则它们需要使用相同的命名空间。

启动新历程时，无法作为第一步放入画布中的元素会被隐藏。 这涉及所有操作、条件活动、等待和反应。

## 快速入门 {#creating_journey}

以下是创建和发布历程的主要步骤。

1. 在顶部菜单中，单击 **[!UICONTROL Home]**&#x200B;选项卡。

   将显示历程列表。 有关该接口的详细信息，请参阅[此页面](../building-journeys/using-the-journey-designer.md)。

   ![](../assets/journey30.png)

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以创建新历程。

   ![](../assets/journey31.png)

1. 编辑右侧显示的配置窗格中的历程属性。请参阅[此页](../building-journeys/changing-properties.md)。

   ![](../assets/journey32.png)

1. 首先，将事件活动从面板拖放到画布中。 您还可以双击某个活动以将其添加到画布中。

   ![](../assets/journey33.png)

1. 拖放其他活动并对其进行配置。 请参阅页面[事件活动](../building-journeys/event-activities.md)、[关于编排活动](../building-journeys/about-orchestration-activities.md)和[关于操作活动](../building-journeys/about-action-activities.md)。

   ![](../assets/journey34.png)

1. 您的历程会自动保存。 测试并发布历程。 请参阅[测试历程](../building-journeys/testing-the-journey.md)和[发布历程](../building-journeys/publishing-the-journey.md)。

   ![](../assets/journey36.png)

## 结束旅程 {#ending_a_journey}

历程可能会因为以下两个原因而终止：

* 人到达了路的最后一个活动。 最后一个活动可以是结束活动或其他活动。 没有义务通过结束活动结束路径。 请参阅[此页](../building-journeys/end-activity.md)。
* 人员到达条件活动（或包含条件的等待活动），且与任何条件都不匹配。

如果允许重新进入，则人员可以重新进入历程。 请参阅[此页](../building-journeys/changing-properties.md)。

由于以下原因，历程可能会关闭：

* 通过&#x200B;**[!UICONTROL Close to new entrances]**&#x200B;按钮手动关闭历程。
* 到达历程的结束日期。

当历程关闭（出于上述任何原因）时，其状态将为&#x200B;**[!UICONTROL Closed]**。 历程将不再允许新人进入历程。 已在历程中的人员将正常完成历程。 在默认的全局超时为30天后，历程将切换到&#x200B;**已完成**&#x200B;状态。 请参阅此[部分](../building-journeys/changing-properties.md#entrance)。

如果您需要阻止历程中所有个人的进度，则可以阻止该进度。 停止历程将超时历程中的所有个人。

要了解如何手动关闭或停止历程，请参阅此[部分](../building-journeys/terminating-a-journey.md)。
