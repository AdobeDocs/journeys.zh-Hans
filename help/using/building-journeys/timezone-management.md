---
product: adobe campaign
title: 时区管理
description: 了解时区管理
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# 时区管理 {#timezone_management}

您可以在中定义时区 [属性](../building-journeys/changing-properties.md) 你旅程的一部分。

要访问属性，请单击屏幕右上角的铅笔图标。

此时区将用于包含时间元素的历程的每个活动，例如：

* [时间条件](../building-journeys/condition-activity.md#time_condition)
* [日期条件](../building-journeys/condition-activity.md#date_condition)
* [自定义等待](../building-journeys/wait-activity.md#custom)

您可以选择时区，也可以选择使用用户配置文件中定义的时区。

>[!NOTE]
>
>配置文件时区与 **时区** 字段存在于 **偏好设置详细信息** 字段组。

## 定义固定时区 {#fixed-timezone}

时区也可以固定。 清除预定义的时区并从下拉列表中选择一个时区。 如果您使用固定时区，则所有进入旅程的个人都将使用相同的时区。

为此，请在中 **[!UICONTROL Properties]**&#x200B;中，选择时区。

![](../assets/journey72.png)

## 使用配置文件定义历程时区 {#timezone-from-profiles}

如果历程的进入事件具有命名空间，这意味着历程可以访问Adobe Experience Platform的实时客户个人资料服务，则您可能希望使用在个人资料级别定义的时区。 为此，请在中 **属性**，检查 **在等待和条件中使用配置文件时区**. 默认情况下不选中此选项。

如果为用户档案定义了时区，则历程将检索并使用它。 如果未指定，则使用的时区将是时区字段中定义的时区。

![](../assets/journey73.png)

## 在表达式中使用时区 {#timezone-in-expressions}

历程的开始和结束日期无法链接到特定时区。 它们会自动关联到实例的时区。
