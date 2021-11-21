---
product: adobe campaign
title: 从一个历程转到另一个历程
description: 从一个历程转到另一个历程
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 4%

---

# 更新用户档案 {#update-profile}

的 **[!UICONTROL Update profile]** 操作活动允许您使用来自事件、数据源或使用特定值的信息来更新现有的Adobe Experience Platform配置文件。

## 重要说明

* 的 **更新用户档案** 操作只能在以具有命名空间的事件开始的历程中使用。
* 该操作仅更新现有字段，而不会创建新的用户档案字段。
* 您不能使用 **更新用户档案** 操作以生成体验事件，例如购买。
* 与任何其他操作一样，在出现错误或超时时，您可以定义替代路径，并且不能同时放置两个操作。
* 发送到Platform的更新请求将会很快，但不会立即/在一秒内发送。 通常需要几秒钟，但有时候需要更多时间，而且无法保证。 因此，例如，如果某个操作使用的是“字段1”，该字段1由位于前面的“更新用户档案”操作更新，则您不应期望该操作中会更新“字段1”。
* 在测试模式下，将不模拟用户档案更新。 将对测试用户档案执行更新。

## 使用用户档案更新

1. 通过以事件开始来设计您的历程。 请参阅 [部分](../building-journeys/journey.md).

1. 在 **操作** ，请将 **更新用户档案** 活动。

   ![](../assets/profileupdate0.png)

1. 从列表中选择架构。

1. 单击 **字段** ，以选择要更新的字段。 只能选择一个字段。

   ![](../assets/profileupdate2.png)

1. 从列表中选择数据集。

   >[!NOTE]
   >
   >的 **更新用户档案** 操作会实时更新配置文件数据，但不会更新数据集。 由于配置文件是与数据集相关的记录，因此需要选择数据集。

1. 单击 **值** 字段来定义要使用的值：

   * 使用简单表达式编辑器，您可以从数据源或传入事件中选择字段。

      ![](../assets/profileupdate4.png)

   * 如果要定义特定值或利用高级函数，请单击 **高级模式**.

      ![](../assets/profileupdate3.png)

的 **更新用户档案** 现已配置。

![](../assets/profileupdate1.png)
