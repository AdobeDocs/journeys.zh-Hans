---
title: 时区管理
description: 了解时区管理
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 2%

---



# 时区管理 {#timezone_management}

您可以在旅程属性中 [定义](../building-journeys/changing-properties.md) 时区。

要访问属性，请单击屏幕右上方的铅笔图标。

此时区将用于旅程中包含时间元素的每个活动，例如：

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

您可以选择时区或选择使用用户用户档案中定义的时区。

## 定义固定时区 {#fixed-timezone}

时区也可以固定。 清除预定义的时区，并从下拉列表中选择一个时区。 如果您使用固定时区，则所有进入旅程的人都将使用相同的时区。

为此，请在中 **[!UICONTROL Properties]**&#x200B;选择时区。

![](../assets/journey73.png)

## 使用用户档案定义旅程时区 {#timezone-from-profiles}

如果旅程的进入事件具有命名空间，即旅程可以到达Adobe Experience Platform的实时客户用户档案服务，则时区将预定义为在旅程中流入的个人用户档案中指定的时区。

如果在Adobe Experience Platform用户档案中定义了时区，则可以在旅程中检索该时区。

如果个人的用户档案不包含时区，则检索的时区将是时区字段中定义的时区。

为此，请 **[!UICONTROL Properties]**&#x200B;检查 **[!UICONTROL Use Profile timezone in timers and conditions]**。

![](../assets/journey72.png)

## 在表达式中使用时区 {#timezone-in-expressions}

旅程的开始和结束日期不能关联到特定时区。 它们会自动关联到实例的时区。
