---
product: adobe campaign
title: 条件活动
description: 了解条件活动
feature: Journeys
role: User
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 16%

---

# 条件活动{#section_e2n_pft_dgb}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_



提供了四种类型的条件：

* [数据Source条件](#data_source_condition)
* [时间条件](#time_condition)
* [百分比拆分](#percentage_split)
* [日期条件](#date_condition)

![](../assets/journey49.png)

## 关于条件活动 {#about_condition}

在历程中使用多个条件时，您可以为每个条件定义标签，以便更轻松地对其进行识别。

如果要定义多个条件，请单击&#x200B;**[!UICONTROL Add a path]**。 对于每个条件，都会在活动后的画布中添加一个新路径。

![](../assets/journey47.png)

请注意，历程的设计会产生功能影响。 当在条件后定义多个路径时，将仅执行第一个符合条件的路径。 这意味着，可以通过将路径置于彼此上方或下方来更改路径的优先级。

例如，我们以第一个路径的条件“人员是VIP”和第二个路径的条件“人员是男性”为例。 如果同时满足两个条件的人(男性，VIP成员)通过此步骤，那么即使他也符合第二条条件时，也会选择第一条路径，因为第一条路径“以上”。 要更改此优先级，请以其他垂直顺序移动您的活动。

![](../assets/journey48.png)

通过选中&#x200B;**[!UICONTROL Show path for other cases than the one(s) above]**，可以为不符合所定义条件的受众创建其他路径。 请注意，此选项在拆分条件中不可用。 请参阅[百分比拆分](#percentage_split)。

利用简单模式，可根据字段组合执行简单查询。 所有可用的字段都显示在屏幕的左侧。将字段拖放到主区域中。要组合不同元素，请将它们互相联锁，以创建不同的分组和/或分组级别。然后，您可以选择逻辑运算符来组合同一级别上的元素：

* AND：两个条件的交集。 只考虑符合所有条件的元素。
* 或：两个条件的并集。 考虑至少符合一个条件的元素。

![](../assets/journey64.png)

如果您使用[Adobe Experience Platform分段服务](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hans)创建区段，则可以在旅程条件中利用它们。 请参阅[在条件](../segment/using-a-segment.md)中使用区段。


>[!NOTE]
>
>使用简单编辑器无法对时间序列（例如购买列表、过去对消息的点击）执行查询。 为此，您需要使用高级编辑器。 请参阅[此页](../expression/expressionadvanced.md)。

当操作或条件中发生错误时，个人历程将停止。使其继续的唯一方法是选中 **[!UICONTROL Add an alternative path in case of a timeout or an error]** 框。请参阅[此章节](../building-journeys/using-the-journey-designer.md#paths)。

在简单编辑器中，您还可以在事件和数据源类别下找到历程属性类别。 此类别包含与给定用户档案的历程相关的技术字段。 这是系统从实时历程中检索到的信息，如历程 ID 或遇到的特定错误。有关详细信息，请参阅[此页面](../expression/journey-properties.md)

## 数据Source条件 {#data_source_condition}

这允许您根据数据源中的字段或之前位于历程中的事件定义条件。 要了解如何使用表达式编辑器，请参阅[此页面](../expression/expressionadvanced.md)。 使用高级表达式编辑器，您可以设置更高级的条件，以处理集合或使用需要传递参数的数据源。 请参阅[此页](../datasource/external-data-sources.md)。

![](../assets/journey50.png)

## 时间条件{#time_condition}

这样，您就可以根据一天中的小时和/或星期来执行不同的操作。 例如，您可以决定在白天发送短信消息，在工作日夜间发送电子邮件。

>[!NOTE]
>
>时区不再特定于条件，而是现在在历程属性的历程级别定义。 请参见[此页面](../building-journeys/timezone-management.md)。

![](../assets/journey51.png)

## 百分比拆分 {#percentage_split}

此选项允许您随机拆分受众，以为每个组定义不同的操作。 定义每个路径的分割数和重新分区。 拆分计算是统计性的，因为系统无法预测将在历程的这个活动中流动的人数。 因此，分割具有非常低的误差容限。 此函数基于Java随机机制（请参阅此[页面](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)）。

在测试模式下，当达到拆分时，始终选择顶部分支。 如果希望测试选择其他路径，可以重新组织拆分分支的位置。 请参见[此页面](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>请注意，在百分比拆分条件中没有用于添加路径的按钮。 路径的数量将取决于拆分的次数。 在拆分条件中，您无法为其他情况添加路径，因为它不会发生。 人们总是会走上一条不同的道路。

![](../assets/journey52.png)

## 日期条件 {#date_condition}

这允许您根据日期定义不同的流。 例如，如果人员在“销售”期间进入该步骤，您将向他们发送一条特定消息。 一年余下时间里，您将发送另一条消息。

>[!NOTE]
>
>时区不再特定于条件，而是现在在历程属性的历程级别定义。 请参阅[此页](../building-journeys/timezone-management.md)。

![](../assets/journey53.png)

<!--
## Profile cap {#profile_cap}

Use this condition type to set a maximum number of profiles for a journey path. When this limit is reached, the selected profiles take a second path.

You can use this condition type to ramp up the volume of your deliveries. For example, you might have recently moved to another email service provider, IP address, or email domain or subdomain. Using this feature, you can establish your reputation as a sender and avoid that your deliveries be blocked or moved to the spam folder of the recipients' mailbox. Learn how to increase your email reputation with IP warming in the [Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=zh-Hans){target="_blank"}.

The default cap is 1000. You must set an integer value that is greater than or equal to 1.

The counter applies only to the selected journey version. By default, the counter is reset to zero after 180 days. After a reset, the selected profiles take the first path again until the counter limit is reached. You can gradually increase this limit up to the total number of your subscribers. After your IP has warmed up, you can remove this condition.

The first path always has priority over the second path, even if you move the second path above the first path on the journey canvas.

![](../assets/profile-cap-condition.png)
-->