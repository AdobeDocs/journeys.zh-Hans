---
title: 区段触发活动
description: 进一步了解细分触发器
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b66cdb31b62b4627ff7378e48879ffadfedda5cb
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---


# 区段触发活动 {#segment-trigger-activity}

## 关于区段触发活动 {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>如果在发布时间或测试模式Adobe Campaign Standard时画布中存在现成激活操作活动，则旅程将在每秒13个入口时进行限流。 <br>如果在发布时或测试模式Adobe Campaign Standard时画布中没有现成的活动，则旅程将以每秒1000事件限制。

区段触发活动允许您让属于Adobe Experience Platform区段的所有个人进入旅程。 进入旅程可以执行一次，也可以定期执行。

假设您在Adobe Experience Platform方面拥有黄金客户细分。 利用细分触发活动，您可以让黄金客户细分的所有个人进入旅程，并使其进入个性化旅程，利用所有旅程功能： 条件、计时器、事件、动作。

## 配置活动 {#configuring-segment-trigger-activity}

>[!NOTE]
>
>由于细分导出延迟，无法在1小时以内的较短时间内触发基于细分的旅程。

1. 展开 **[!UICONTROL Orchestration]** 类别并将 **[!UICONTROL Segment Trigger]** 活动放入画布。

   活动必须定位为旅程的第一步。

1. 配置活动 **[!UICONTROL Scheduler type]**。

   默认情况下，区段将进入旅程， **[!UICONTROL As soon as possible]**&#x200B;即在旅程发布后1小时进入。 如果要让区段在特定日期／时间或定期输入旅程，请从列表中选择所需的选项。

   如果出现重复旅程，您还可以定义旅程的开始和结束。

   ![](../assets/segment-trigger-schedule.png)

1. 在字 **[!UICONTROL Segment]** 段中，选择将进入旅程的Adobe Experience Platform区段，然后单击 **[!UICONTROL Save]**。

   ![](../assets/segment-trigger-segment-selection.png)

1. 在字 **[!UICONTROL Namespace]** 段中，选择要使用的命名空间以识别个人。 For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >属于某个细分的个人，如果其不同身份之间没有选定的身份(命名空间)，则不能进入旅程。

1. Click **[!UICONTROL Ok]** to confirm. 然后，您可以利用可用活动构建您的旅程。

1. 旅程准备就绪后，您可以测试它(请参 [阅测试旅程](../building-journeys/testing-the-journey.md))。

   在从活动开始的旅程中激活测试模式 **[!UICONTROL Segment Trigger]** 时，将在符合所选段条件的用户档案中随机选择100个测试用户档案。 测试日志将允许您查看旅程中个人的路径以及可能遇到的错误(请参 [阅查看日志](../building-journeys/testing-the-journey.md#viewing_logs))。

   >[!NOTE]
   >
   >请注意，您将无法使用单一旅程中现有的视觉流功能来查看旅程后的100人。

1. 然后，您可以发布您的旅程(请 [参阅发布旅程](../building-journeys/publishing-the-journey.md))。 属于该区段的个人将在“区段触发器”活动调度程序中指定的日期／时间进入旅程。

   >[!IMPORTANT]
   >
   >请记住，Adobe Experience Platform细分每天计算一次(批&#x200B;**细分** )或实时计算(流&#x200B;**化细分** )。
   >
   >如果对所选区段进行流处理，属于此区段的个人可能会实时进入该旅程。 如果区段为批，则新符合此区段资格的人员将潜在地在对Adobe Experience Platform执行区段计算时进入旅程。
