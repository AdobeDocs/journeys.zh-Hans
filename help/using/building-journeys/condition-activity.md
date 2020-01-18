---
title: 条件活动
description: 了解条件活动
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
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c

---


# 条件活动{#section_e2n_pft_dgb}

有四种条件可用：

* [数据源条件](#data_source_condition)
* [时间条件](#time_condition)
* [拆分百分比](#percentage_split)
* [日期条件](#date_condition)

![](../assets/journey49.png)

## 关于“条件”活动 {#about_condition}

如果 **[!UICONTROL Add a path]**要定义多个条件，请单击。 对于每个条件，在活动之后的画布中会添加新路径。

![](../assets/journey47.png)

请注意，旅程设计会对功能产生影响。 在条件后定义多个路径时，将只执行第一个符合条件的路径。 这意味着，您可以通过将路径彼此置于上方或下方来改变路径的优先级。 例如，如果第一个路径的条件是“人是VIP”，而第二个路径的条件是“人是男性”。 如果符合这两个条件的人员（VIP男性）通过此步骤，则即使他也有资格获得第二个路径，也将选择第一个路径，因为第一个路径“高于”。 要更改此优先级，请按另一个垂直顺序移动活动。

![](../assets/journey48.png)

您可以通过选中为不符合定义条件的受众创建其他路径 **[!UICONTROL Show path for other cases than the one(s) above]**。 请注意，此选项在拆分条件中不可用。 请参[阅拆分百分比](#percentage_split)。

简单模式允许您基于字段组合执行简单查询。 所有可用字段都显示在屏幕的左侧。 将字段拖放到主区域。 要组合不同的元素，请将它们彼此互锁以创建不同的组和／或组级别。 然后，您可以选择逻辑运算符来组合同一级别上的元素：

* 和：两个标准的交集。 只考虑与所有条件匹配的元素。
* 或：两个标准的结合。 考虑与两个标准中的至少一个匹配的元素。

![](../assets/journey64.png)

>[!NOTE]
>
>不能使用简单的编辑器对时间序列执行查询（例如，购买列表、消息的点击次数）。 为此，您需要使用高级编辑器。 请参见 [](../expression/expressionadvanced.md)。

## 数据源条件 {#data_source_condition}

这允许您根据数据源中的字段或先前位于旅程中的事件定义条件。 要了解如何使用表达式编辑器，请参阅 [](../expression/expressionadvanced.md)。 使用高级表达式编辑器，您可以设置更高级的条件来处理集合或使用要求传递参数的数据源。 请参见 [](../datasource/external-data-sources.md)。

![](../assets/journey50.png)

## 时间条件{#time_condition}

这允许您根据一天中的某小时和／或一周中的某天执行不同的操作。 例如，您可以决定在白天发送SMS消息，在工作日晚上发送电子邮件。 您可以为此条件定义特定时区。 请参见 [](../building-journeys/timezone-management.md)。

![](../assets/journey51.png)

## 拆分百分比 {#percentage_split}

此选项允许您随机拆分受众以为每个组定义不同的操作。 定义每个路径的拆分数和重新分区。 分割计算是统计的，因为系统无法预测在旅程中会有多少人流。 因此，分割具有非常低的误差裕度。 此函数基于Java随机机制(请参阅 [此页](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html))。

>[!NOTE]
>
>请注意，在百分比拆分条件中没有添加路径的按钮。 路径数取决于拆分数。 在拆分条件中，您无法为其他情况添加路径，因为它不可能发生。 人们将始终进入一个分割路径。


![](../assets/journey52.png)

## 日期条件 {#date_condition}

这允许您根据日期定义不同的流。 例如，如果人员在“销售”期间进入步骤，您将向他发送特定消息。 在一年的其余时间，您会再发送一条消息。 定义日期条件时，必须指定时区。 请参见 [](../building-journeys/timezone-management.md)。

![](../assets/journey53.png)
