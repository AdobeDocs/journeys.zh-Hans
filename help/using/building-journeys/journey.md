---
product: adobe campaign
solution: Journey Orchestration
title: 关于历程构建
description: 作为企业用户，了解如何结合事件、编排和行为活动来构建历程。
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 409197458ba32f9fdb3e42e4b06eae2814eff9f8
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 13%

---


# 创建历程 {#concept_gq5_sqt_52b}

此步骤由&#x200B;**业务用户**&#x200B;执行。 这是您创造旅程的地方。 结合不同的事件、编排和操作活动，构建多步跨渠道方案。

旅程界面允许您将调色板中的活动轻松拖放到画布中。 您还可以在下一个可用步骤中，多次单击某个活动，将其添加到画布中。 每个活动在流程中都具有特定的角色和位置。 活动被排序。 完成活动后，流将继续并处理下一个活动，依此类推。

每个旅程只允许一个命名空间。 放置第一个事件时，具有不同命名空间的事件将灰显。 如果第一个事件没有命名空间，则具有命名空间的所有事件将灰显。 请参阅[此页](../event/selecting-the-namespace.md)。此外，如果旅程包含没有命名空间的事件,Adobe Experience Platform字段组将灰显。 最后，如果您在同一旅程中使用多个事件，他们需要使用相同的命名空间。

开始新旅程时，无法作为第一步在画布中放置的元素会被隐藏。 这涉及所有行动、条件活动、等待和反应。

## 快速开始{#creating_journey}

以下是创建和发布旅程的主要步骤。

1. 在顶部菜单中，单击 **[!UICONTROL Home]**&#x200B;选项卡。

   将显示旅程列表。 有关接口的详细信息，请参阅[此页](../building-journeys/using-the-journey-designer.md)。

   ![](../assets/journey30.png)

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以创建新旅程。

   ![](../assets/journey31.png)

1. 编辑右侧显示的配置窗格中的历程属性。请参阅[此页](../building-journeys/changing-properties.md)。

   ![](../assets/journey32.png)

1. 开始，方法是将事件活动从调色板中拖放到画布中。 您还可以按住多次单击某个活动，将其添加到画布。

   ![](../assets/journey33.png)

1. 拖放其他活动并配置它们。 请参阅[事件活动](../building-journeys/event-activities.md)、[关于业务流程活动](../building-journeys/about-orchestration-activities.md)和[关于操作活动](../building-journeys/about-action-activities.md)页。

   ![](../assets/journey34.png)

1. 您的旅程将自动保存。 测试旅程并发布。 请参阅[测试旅程](../building-journeys/testing-the-journey.md)和[发布旅程](../building-journeys/publishing-the-journey.md)。

   ![](../assets/journey36.png)

## 结束旅程{#ending_a_journey}

一个旅程可能会因个人而结束，原因有二：

* 那人到达了路的最后活动。 最后一个活动可以是结束活动或其他活动。 没有义务用结束活动结束路径。 请参阅[此页](../building-journeys/end-activity.md)。
* 该人到达条件活动(或具有条件的等待活动)，并且不符合任何条件。

如果允许重新进入，则人员随后可以重新进入旅程。 请参阅[此页](../building-journeys/changing-properties.md)。

由于以下原因，旅程可能会结束：

* 通过&#x200B;**[!UICONTROL Close to new entrances]**&#x200B;按钮手动关闭旅程。
* 到达旅程的结束日期。

当旅程关闭时（出于上述任何原因），其状态将为&#x200B;**[!UICONTROL Closed (no entrance)]**。 这一旅程将不再让新人进入旅程。 已经在旅程中的人将正常完成旅程。 在默认全局超时30天后，旅程将切换到&#x200B;**已完成**&#x200B;状态。 请参阅此[部分](../building-journeys/changing-properties.md#entrance)。

如果您需要阻止旅程中所有个人的进步，您可以阻止它。 停止旅程将超时旅程中的所有个人。

要了解如何手动关闭或停止旅程，请参阅此[部分](../building-journeys/terminating-a-journey.md)。