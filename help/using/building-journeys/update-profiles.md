---
product: adobe campaign
title: 更新用户档案
description: 更新用户档案
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 64f415f3a4120685b64a4b1dc15bf004e86b35d2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# 更新用户档案 {#update-profile}

此 **[!UICONTROL Update profile]** 利用操作活动，可使用来自事件、数据源的信息或使用特定值更新现有Adobe Experience Platform用户档案。

## 重要说明

* 此 **更新配置文件** 操作只能在以具有命名空间的事件开始的历程中使用。
* 该操作仅更新现有字段，不创建新配置文件字段。
* 您不能使用 **更新配置文件** 用于生成体验事件的操作，例如购买。
* 与任何其他操作一样，您可以定义在发生错误或超时时的替代路径，并且不能同时设置两个操作。
* 发送到Platform的更新请求将快速完成，但不会立即/在一秒内。 通常需要几秒钟的时间，但有时需要更长时间，无法保证。 因此，例如，如果某个操作正在使用由之前放置的“更新用户档案”操作更新的“字段1”，则不应期望该操作中会更新“字段1”。
* 在测试模式下，将不会模拟用户档案更新。 将对测试用户档案执行更新。
* 此 **更新配置文件** 活动不支持定义为枚举的XDM字段。

## 使用用户档案更新

1. 从事件开始设计您的旅程。 请参阅此[部分](../building-journeys/journey.md)。

1. 在 **操作** 部分，拖放 **更新配置文件** 活动移入画布。

   ![](../assets/profileupdate0.png)

1. 从列表中选择架构。

1. 单击 **字段** 以选择要更新的字段。 只能选择一个字段。

   ![](../assets/profileupdate2.png)

1. 从列表中选择数据集。

   >[!NOTE]
   >
   >此 **更新配置文件** 操作可实时更新用户档案数据，但不会更新数据集。 需要选择数据集，因为用户档案是与数据集相关的记录。

1. 单击 **值** 字段以定义要使用的值：

   * 使用简单表达式编辑器，您可以从数据源或传入事件中选择字段。

     ![](../assets/profileupdate4.png)

   * 如果要定义特定值或利用高级函数，请单击 **高级模式**.

     ![](../assets/profileupdate3.png)

此 **更新配置文件** 现已配置。

![](../assets/profileupdate1.png)
