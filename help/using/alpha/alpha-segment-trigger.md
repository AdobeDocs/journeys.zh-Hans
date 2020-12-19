---
product: adobe campaign
solution: Journey Orchestration
title: “读取区段”活动
description: 进一步了解阅读区段活动。
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 3%

---


# “读取区段”活动{#segment-trigger-activity}

## 关于读取段活动{#about-segment-trigger-actvitiy}

>[!NOTE]
>
>如果在发布时间或测试模式Adobe Campaign Standard时画布中存在激活现成的操作活动，则旅程将在每秒13个入口处被限制。 否则，旅程将以每秒1000事件的速度减速。

阅读区段活动允许您让属于Adobe Experience Platform区段的所有个人进入旅程。 进入旅程的操作可以执行一次，也可以定期执行。

假设您在Adobe Experience Platform拥有黄金客户细分。 通过阅读细分活动，您可以让属于黄金客户细分的所有个人进入旅程，并让他们进入个性化旅程，利用所有旅程功能：条件、计时器、事件、动作。

>[!NOTE]
>
>在同一旅程中，不能有跳转和&#x200B;**读取段**&#x200B;活动。 您不能跳到具有&#x200B;**读取段**&#x200B;开始的旅程。

## 配置活动{#configuring-segment-trigger-activity}

>[!NOTE]
>
>由于细分导出延迟，无法在1小时以内的较短时间内触发基于细分的旅程。

1. 打开&#x200B;**[!UICONTROL Orchestration]**&#x200B;类别，将&#x200B;**[!UICONTROL Read Segment]**&#x200B;活动放入画布。

   活动必须定位为旅程的第一步。

1. 将&#x200B;**[!UICONTROL Label]**&#x200B;添加到活动（可选）。

1. 在&#x200B;**[!UICONTROL Segment]**&#x200B;字段中，选择将进入旅程的Adobe Experience Platform区段，然后单击&#x200B;**[!UICONTROL Save]**。

   >[!NOTE]
   >
   >请注意，您可以自定义列表中显示的列，并对其进行排序。

   ![](../assets/segment-trigger-segment-selection.png)

   添加区段后，**[!UICONTROL Copy]**&#x200B;按钮允许您复制其名称和ID:

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. 在&#x200B;**[!UICONTROL Namespace]**&#x200B;字段中，选择要用于识别个人的命名空间。 有关命名空间的详细信息，请参阅[此部分](../event/selecting-the-namespace.md)。

   >[!NOTE]
   >
   >属于某个细分的个人，如果其不同身份之间没有选定的身份(命名空间)，则不能进入旅程。

1. **[!UICONTROL Read Segment]**&#x200B;活动允许您指定段进入旅程的时间。 为此，请单击&#x200B;**[!UICONTROL Edit journey schedule]**&#x200B;链接以访问旅程的属性，然后配置&#x200B;**[!UICONTROL Scheduler type]**&#x200B;字段。

   ![](../assets/segment-trigger-schedule.png)

   默认情况下，区段会输入旅程&#x200B;**[!UICONTROL As soon as possible]**，即旅程发布后1小时。 如果要让区段在特定日期／时间或定期输入旅程，请从列表中选择所需值。

   >[!NOTE]
   >
   >请注意，**[!UICONTROL Schedule]**&#x200B;部分仅在画布中放置了&#x200B;**[!UICONTROL Read Segment]**&#x200B;活动时可用。

   ![](../assets/segment-trigger-properties.png)

## 测试和发布旅程{#testing-publishing}

**[!UICONTROL Read Segment]**&#x200B;活动允许您在单一用户档案或100个随机测试用户档案上测试旅程，这些在符合段条件的用户档案中选择。

为此，请激活测试模式，然后从左窗格中选择所需的选项。

![](../assets/segment-trigger-test-modes.png)

然后，可以像往常一样配置和运行测试模式。 有关如何测试旅程的详细步骤，请参见[本节](../building-journeys/testing-the-journey.md)。

测试运行后，**[!UICONTROL Show logs]**&#x200B;按钮允许您根据选定的测试选项查看测试结果：

* **[!UICONTROL Single profile at a time]**:测试日志显示与使用单一测试模式时相同的信息。有关详细信息，请参阅[此部分](../building-journeys/testing-the-journey.md#viewing_logs)

* **[!UICONTROL Up to 100 profiles at once]**:通过测试日志，您可以跟踪从Adobe Experience Platform出口区段的进度以及所有进入旅程的人员的个人进度。

   请注意，一次使用最多100个用户档案测试旅程不允许您使用视觉流跟踪旅程中个人的进度。

   ![](../assets/read-segment-log.png)

测试成功后，您可以发布旅程（请参阅[发布旅程](../building-journeys/publishing-the-journey.md)）。 属于该区段的个人将在旅程的属性&#x200B;**[!UICONTROL Scheduler]**&#x200B;部分中指定的日期／时间进入旅程。

>[!NOTE]
>
>在执行不再重复（尽快开始或“一次”）的基于细分的旅程的新版本时，之前进入该旅程的所有个人在发布该旅程时不会重新输入其新版本。 如果您希望允许他们重新进入，您应该重复旅程。
