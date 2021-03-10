---
product: adobe campaign
solution: Journey Orchestration
title: 时区管理
description: 了解时区管理
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 2%

---



# 时区管理 {#timezone_management}

您可以在旅程的[属性](../building-journeys/changing-properties.md)中定义时区。

要访问“属性”，请单击屏幕右上角的铅笔图标。

此时区将用于包含时间元素的旅程的每个活动，例如：

* [时间条件](../building-journeys/condition-activity.md#time_condition)
* [日期条件](../building-journeys/condition-activity.md#date_condition)
* [自定义等待](../building-journeys/wait-activity.md#custom)
* [固定日期等待](../building-journeys/wait-activity.md#fixed_date)

您可以选择时区或选择使用在用户用户档案中定义的时区。

## 定义固定时区{#fixed-timezone}

时区也可以固定。 清除预定义的时区，并从下拉列表中选择一个时区。 如果您使用固定时区，则所有进入旅程的个人都使用相同的时区。

要执行此操作，请在&#x200B;**[!UICONTROL Properties]**&#x200B;中选择时区。

![](../assets/journey73.png)

## 使用用户档案定义旅程时区{#timezone-from-profiles}

如果旅程的进入事件具有命名空间，即旅程可以到达Adobe Experience Platform的实时客户用户档案服务，则时区将预定义为流入旅程的个人用户档案中指定的时区。

如果在Adobe Experience Platform用户档案中定义时区，则可以在旅程中检索该时区。

如果个人的用户档案不包含时区，则检索的时区将是时区字段中定义的时区。

要执行此操作，请在&#x200B;**[!UICONTROL Properties]**&#x200B;中选中&#x200B;**[!UICONTROL Use Profile timezone in timers and conditions]**。

![](../assets/journey72.png)

## 在表达式{#timezone-in-expressions}中使用时区

旅程的开始和结束日期不能链接到特定时区。 它们会自动与实例的时区关联。
