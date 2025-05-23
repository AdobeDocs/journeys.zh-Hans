---
product: adobe campaign
title: 从一个历程转到另一个历程
description: 从一个历程转到另一个历程
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 5%

---

# 从一个历程转到另一个历程 {#jump}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_



**[!UICONTROL Jump]**&#x200B;操作活动允许您将个人从一个历程推送到另一个历程。 此功能允许您：

* 通过将非常复杂的历程分成若干个历程来简化其设计
* 基于通用且可重用的历程模式构建历程

在起源历程中，只需添加&#x200B;**[!UICONTROL Jump]**&#x200B;活动并选择目标历程即可。 当个人进入&#x200B;**[!UICONTROL Jump]**&#x200B;步骤时，内部事件将发送到目标历程的第一个事件。 如果&#x200B;**[!UICONTROL Jump]**&#x200B;操作成功，个人将继续在历程中前进。 该行为与其他操作类似。

在目标历程中，**[!UICONTROL Jump]**&#x200B;活动在内部触发的第一个事件将生成历程中的单个流程。

## 生命周期

假设您已将历程A中的&#x200B;**[!UICONTROL Jump]**&#x200B;活动添加到历程B。历程A是&#x200B;**起源历程**&#x200B;和历程B，**目标历程**。
以下是执行过程的不同步骤：

**历程A**&#x200B;是从外部事件触发的：

1. 历程A接收与个人相关的外部事件。
1. 个人达到&#x200B;**[!UICONTROL Jump]**&#x200B;步骤。
1. 该个人将被推送到历程B，并在&#x200B;**[!UICONTROL Jump]**&#x200B;步骤之后继续到历程A中的后续步骤。

在历程B中，第一个事件通过历程A中的&#x200B;**[!UICONTROL Jump]**&#x200B;活动在内部触发：

1. 历程B从历程A收到了一个内部事件。
1. 个人开始流入历程B。

>[!NOTE]
>
>历程B也可以通过外部事件触发。

## 最佳实践和限制

### 创作

* **[!UICONTROL Jump]**&#x200B;活动仅在使用命名空间的历程中可用。
* 您只能跳转到使用与起源历程相同的命名空间的历程。
* 您无法跳转到以&#x200B;**区段资格**&#x200B;事件开始的历程。
* 您无法在同一历程中具有&#x200B;**[!UICONTROL Jump]**&#x200B;活动和&#x200B;**区段资格**&#x200B;事件。
* 您可以在历程中包含所需数量的&#x200B;**[!UICONTROL Jump]**&#x200B;个活动。 在&#x200B;**[!UICONTROL Jump]**&#x200B;之后，您可以添加所需的任何活动。
* 您可以根据需要设置任意多个跳转级别。 例如，历程A跳转到旅程B，再跳转到旅程C，等等。
* 目标历程还可以根据需要包含任意数量的&#x200B;**[!UICONTROL Jump]**&#x200B;活动。
* 不支持循环模式。 无法将两个或更多历程链接在一起，这会产生无限循环。 **[!UICONTROL Jump]**&#x200B;活动配置屏幕阻止您执行此操作。

### 执行

* 执行&#x200B;**[!UICONTROL Jump]**&#x200B;活动时，将触发目标历程的最新版本。
* 像往常一样，同一个历程中只能出现一次独特个人。 因此，如果从起源历程推送的个人已在目标历程中，则该个人将不会进入目标历程。 **[!UICONTROL Jump]**&#x200B;活动不会报告任何错误，因为这是正常行为。

## 配置跳转活动

1. 设计您的&#x200B;**起源历程**。

   ![](../assets/jump1.png)

1. 在历程的任何步骤，从&#x200B;**[!UICONTROL ACTIONS]**&#x200B;类别添加&#x200B;**[!UICONTROL Jump]**&#x200B;活动。 添加标签和描述。

   ![](../assets/jump2.png)

1. 在&#x200B;**目标历程**&#x200B;字段中单击。
列表会显示草稿、实时或测试模式中的所有历程版本。 使用其他命名空间或以&#x200B;**区段鉴别**&#x200B;历程开头的事件不可用。 还会过滤掉会创建循环模式的目标历程。

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >您可以单击右侧的&#x200B;**打开目标历程**&#x200B;图标，以在新选项卡中打开目标历程。

1. 选择要跳转到的目标历程。
**First event**&#x200B;字段已使用目标历程第一个事件的名称预填充。 如果您的目标历程包含多个事件，则仅允许在第一个事件中使用&#x200B;**[!UICONTROL Jump]**。

   ![](../assets/jump4.png)

1. **操作参数**&#x200B;部分显示目标事件的所有字段。 与其他类型的操作一样，将每个字段映射到来自源事件或数据源的字段。 此信息将在运行时传递到目标历程。
1. 添加后续活动以完成您的起源历程。

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >个人身份会自动映射。 此信息在界面中不可见。

您的&#x200B;**[!UICONTROL Jump]**&#x200B;活动已配置。 一旦您的历程处于实时状态或测试模式，到达&#x200B;**[!UICONTROL Jump]**&#x200B;步骤的个人将从推送到目标历程。

在历程中配置&#x200B;**[!UICONTROL Jump]**&#x200B;活动时，将在目标历程的开头自动添加&#x200B;**[!UICONTROL Jump]**&#x200B;条目图标。 这有助于您确定历程既可以从外部触发，也可以从内部从&#x200B;**[!UICONTROL Jump]**&#x200B;活动触发。

![](../assets/jump7.png)

## 故障排除

发布历程或处于测试模式时，如果出现以下情况，将发生错误：
* 目标历程不再存在
* 目标历程为草稿、已关闭或已停止
* 如果目标历程的第一个事件已更改并且映射已损坏

![](../assets/jump6.png)
