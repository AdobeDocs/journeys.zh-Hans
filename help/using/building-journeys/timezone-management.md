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
source-git-commit: f4f41428b19f611da15b20a1788b240fadfd49fa

---



# 时区管理 {#timezone_management}

您可以在旅程的属性中 [定义](../building-journeys/changing-properties.md) 时区。

要访问“属性”，请单击屏幕右上角的铅笔图标。

此时区将用于包含时间元素的旅程中的每个活动，例如：

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

您可以选择时区或选择使用用户配置文件中定义的时区。

## 定义固定时区 {#fixed-timezone}

时区也可以固定。 清除预定义的时区，并从下拉列表中选择一个时区。 如果您使用固定时区，则所有进入该旅程的人都会使用相同的时区。

为此，请在中 **[!UICONTROL Properties]**&#x200B;选择一个时区。

![](../assets/journey73.png)

## 使用配置文件定义旅程时区 {#timezone-from-profiles}

如果旅程的进入事件具有命名空间，即旅程可以到达数据平台的实时客户档案服务，则时区将用旅程中流入的个人档案中指定的时区进行预定义。

如果在Experience platform配置文件中定义了时区，则可在旅程中检索该时区。

如果个人的配置文件不包含时区，则检索到的时区将是时区字段中定义的时区。

为此，请 **[!UICONTROL Properties]**&#x200B;查看 **[!UICONTROL Use Profile timezone in timers and conditions]**。

![](../assets/journey72.png)

## 在表达式中使用时区 {#timezone-in-expressions}

时区用于使用高级表达式编辑器构建表达式。 在这种情况下，您将使用表达式编辑器选择您希望系统获取此信息的位置。 请参见 [](../expression/expressionadvanced.md)。

旅程的开始和结束日期不能与特定时区关联。 它们会自动关联到实例的时区。
