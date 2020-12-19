---
product: adobe campaign
solution: Journey Orchestration
title: 区段鉴别事件
description: 了解细分资格事件
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---


# 区段鉴别事件 {#segment-qualification}

## 关于段资格事件{#about-segment-qualification}

此活动允许您的旅程倾听Adobe Experience Platform地区用户档案入口和出口，以便让个人进入旅程或前进。 有关区段创建的详细信息，请参阅此[部分](../segment/about-segments.md)。

假设您拥有“银色客户”细分。 通过此活动，您可以让所有新的银质客户进入旅程，并向他们发送一系列个性化信息。

此类事件可定位为旅程的第一步或稍后步骤。

>[!IMPORTANT]
>
>请记住，Adobe Experience Platform区段每天计算一次（**批**&#x200B;段）或实时计算(**streamed**&#x200B;段，使用Adobe Experience Platform的高频受众选项)。
>
>如果对所选区段进行流处理，属于此区段的个人可能会实时进入该旅程。 如果区段为批，则新符合此区段资格的人员将潜在地在在Adobe Experience Platform执行区段计算时进入旅程。


1. 打开&#x200B;**[!UICONTROL Events]**&#x200B;类别，将&#x200B;**[!UICONTROL Segment qualification]**&#x200B;活动放入画布。

   ![](../assets/segment5.png)

1. 将&#x200B;**[!UICONTROL Label]**&#x200B;添加到活动。 此步骤是可选的。

1. 单击&#x200B;**[!UICONTROL Segment]**&#x200B;字段，然后选择要利用的区段。

   >[!NOTE]
   >
   >请注意，您可以自定义列表中显示的列，并对其进行排序。

   ![](../assets/segment6.png)

   添加区段后，**[!UICONTROL Copy]**&#x200B;按钮允许您复制其名称和ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. 在&#x200B;**[!UICONTROL Behavior]**&#x200B;字段中，选择是您要侦听段入口、出口或两者。

1. 选择命名空间。 仅当将事件定位为旅程的第一步时，才需要此设置。

   ![](../assets/segment7.png)

有效负荷包含以下上下文信息，您可以在条件和操作中使用这些信息：

* 行为（入口、出口）
* 资格时间戳
* 区段id

在&#x200B;**[!UICONTROL Segment qualification]**&#x200B;表达式后的条件或操作中使用活动编辑器时，您有权访问&#x200B;**[!UICONTROL SegmentQualification]**&#x200B;节点。 您可以选择&#x200B;**[!UICONTROL Last qualification time]**&#x200B;和&#x200B;**[!UICONTROL status]**（进入或退出）。

请参阅[条件活动](../building-journeys/condition-activity.md#about_condition)。

![](../assets/segment8.png)

## 最佳做法 {#best-practices-segments}

**[!UICONTROL Segment Qualification]**&#x200B;活动允许在Adobe Experience Platform某段获得资格或被取消资格的个人在旅程中立即进入。

该信息的接收速度很快。 所做的测量显示每秒接收10,000事件的速度。 因此，你应该确保你明白入口高峰是如何发生的，如何避开它们，以及如何让你的旅程为它们做好准备。

### 批处理段{#batch-speed-segment-qualification}

在对批处理段使用段资格时，请注意，在每日计算时将出现入口高峰。 峰值的大小取决于每天进入（或退出）区段的个人数。

此外，如果新创建批段并立即在旅程中使用，则第一批计算可能会使大量个人进入旅程。

### 流化段{#streamed-speed-segment-qualification}

当对流化分段使用分段资格时，由于持续评估分段，导致入口／出口出现较大高峰的风险较小。 但是，如果细分定义导致大量客户同时获得相应资格，则可能也会出现峰值。

有关流分段的详细信息，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### 如何避免过载{#overloads-speed-segment-qualification}

以下是有助于避免在旅程中利用超载系统(数据源、自定义操作、Adobe Campaign Standard操作)的一些最佳实践。

在&#x200B;**[!UICONTROL Segment Qualification]**&#x200B;活动中，请勿在创建批区段后立即使用它。 它将避免第一个计算峰。 请注意，如果您要使用从未计算过的区段，旅程画布中将显示黄色警告。

![](../assets/segment-error.png)

为数据源设置上限规则，并在旅程中使用操作，以避免超载（请参阅此[部分](../api/capping.md)）。 请注意，限制规则没有重试。 如果需要重试，则必须在旅程中选中条件或操作中的&#x200B;**[!UICONTROL Add an alternative path in case of a timeout or an error]**&#x200B;框，以使用替代路径。

在制作旅程中使用细分之前，请始终首先评估每天符合此细分条件的个人数量。 为此，您可以检查Adobe Experience Platform的&#x200B;**[!UICONTROL Segments]**&#x200B;部分并查看右侧的图形。

![](../assets/segment-overload.png)
