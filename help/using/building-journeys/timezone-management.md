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
source-wordcount: '276'
ht-degree: 9%

---

# 时区管理 {#timezone_management}

您可以在历程的[属性](../building-journeys/changing-properties.md)中定义时区。

要访问属性，请单击屏幕右上角的铅笔图标。

此时区将用于包含时间元素的历程的每个活动，例如：

* [时间条件](../building-journeys/condition-activity.md#time_condition)
* [日期条件](../building-journeys/condition-activity.md#date_condition)
* [自定义等待](../building-journeys/wait-activity.md#custom)

您可以选择时区，也可以选择使用用户配置文件中定义的时区。

>[!NOTE]
>
>配置文件时区与&#x200B;**首选项详细信息**&#x200B;字段组中现有的&#x200B;**时区**&#x200B;字段一起使用。

## 定义固定时区 {#fixed-timezone}

时区也可以固定。 清除预定义的时区并从下拉列表中选择一个时区。 如果您使用固定时区，则所有进入旅程的个人都将使用相同的时区。

为此，请在&#x200B;**[!UICONTROL Properties]**&#x200B;中选择时区。

![](../assets/journey72.png)

## 使用配置文件定义历程时区 {#timezone-from-profiles}

如果历程的进入事件具有命名空间，这意味着历程可以访问Adobe Experience Platform的实时客户个人资料服务，则您可能希望使用在个人资料级别定义的时区。 为此，请在&#x200B;**属性**&#x200B;中选中&#x200B;**在等待和条件中使用配置文件时区**。 默认情况下不选中此选项。

如果已为配置文件定义了时区，则该历程将会检索并使用该时区。如果未指定，则使用的时区将是时区字段中定义的时区。

![](../assets/journey73.png)

## 在表达式中使用时区 {#timezone-in-expressions}

历程的开始和结束日期无法链接到特定时区。 它们会自动关联到实例的时区。
