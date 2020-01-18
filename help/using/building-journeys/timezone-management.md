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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# 时区管理 {#timezone_management}

时区定义在以下活动中可用：

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

如果旅程的进入事件具有命名空间，即旅程可以到达数据平台的实时客户档案服务，则时区将用旅程中流入的个人档案中指定的时区进行预定义。 如果个人的配置文件不包含时区，则使用实例的时区。 您可以联系管理员以了解实例时区。

![](../assets/journey73.png)

时区也可以固定。 清除预定义的时区，并从下拉列表中选择一个时区。 如果您使用固定时区，则所有进入该旅程的人都会使用相同的时区。

![](../assets/journey72.png)

最后，每个进入该步骤的人都可以动态地显示时区。 在这种情况下，您将使用表达式编辑器选择您希望系统获取此信息的位置（该信息可能来自事件或数据源）。 请参见 [](../expression/expressionadvanced.md)。


旅程的开始和结束日期不能与特定时区关联。 它们会自动关联到实例的时区。
