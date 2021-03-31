---
product: adobe campaign
solution: Journey Orchestration
title: 从一个历程到另一个历程
description: 从一个历程到另一个历程
feature: 历程
role: 商业从业者
level: 中间
translation-type: tm+mt
source-git-commit: 7123cff30039d6a5174b0272db33e4a9d15d4ca9
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 5%

---


# 更新用户档案 {#update-profile}

**[!UICONTROL Update profile]**&#x200B;操作活动允许您使用来自事件、数据源或使用特定值的信息更新现有Adobe Experience Platform用户档案。

## 重要说明

* **更新用户档案**&#x200B;动作只能用于从具有命名空间的事件开始的旅程。
* 该操作只更新现有字段，不会创建新的用户档案字段。
* 您不能使用&#x200B;**更新用户档案**&#x200B;操作生成体验事件，例如购买。
* 与任何其他操作一样，您可以在出现错误或超时时定义替代路径，并且不能并行放置两个操作。
* 发送到平台的更新请求将会很快，但不会立即/在一秒内。 通常需要几秒钟，但有时候还需要更多时间，而无法保证。 因此，例如，如果某个操作使用的是“字段1”，而“字段1”是由位于前面的“更新用户档案”操作更新的，则您不应期望该操作中会更新“字段1”。
* 数据源在字段组级别具有缓存持续时间的概念。 如果您希望在旅程中利用最近更新的用户档案字段，请务必定义非常短的缓存持续时间。
* 在测试模式下，不会模拟用户档案更新。 将对测试用户档案执行更新。

## 使用用户档案更新

1. 从事件开始，设计您的旅程。 请参阅此[部分](../building-journeys/journey.md)。

1. 在调色板的&#x200B;**Action**&#x200B;部分，将&#x200B;**更新用户档案**&#x200B;活动放入画布中。

   ![](../assets/profileupdate0.png)

1. 从模式中选择列表。

1. 单击&#x200B;**字段**&#x200B;以选择要更新的字段。 只能选择一个字段。

   ![](../assets/profileupdate2.png)

1. 从列表中选择数据集。 用户档案集选择将确定存储字段新值的位置。

1. 单击&#x200B;**值**&#x200B;字段以定义要使用的值：

   * 使用简单的表达式编辑器，您可以从数据源或传入事件中选择字段。

      ![](../assets/profileupdate4.png)

   * 如果要定义特定值或利用高级函数，请单击&#x200B;**高级模式**。

      ![](../assets/profileupdate3.png)

**更新用户档案**&#x200B;现已配置。

![](../assets/profileupdate1.png)
