---
product: adobe campaign
title: 从一个历程转到另一个历程
description: 从一个历程转到另一个历程
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---

# 从一个历程转到另一个历程 {#jump}

的 **[!UICONTROL Jump]** 操作活动允许您将个人从一个历程推送到另一个历程。 此功能允许您：

* 通过将非常复杂的历程分成若干个历程来简化其设计
* 基于通用且可重用的历程模式构建历程

在原始历程中，只需添加 **[!UICONTROL Jump]** 活动，然后选择target历程。 当个人输入 **[!UICONTROL Jump]** 步骤中，将内部事件发送到target历程的第一个事件。 如果 **[!UICONTROL Jump]** 操作成功后，个人将继续在历程中进行。 行为与其他操作类似。

在目标历程中，由 **[!UICONTROL Jump]** 活动将使历程中的各个流量。

>[!NOTE]
>
>另请参阅教程视频 [此处](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=zh-Hans)

## 生命周期

假设您已添加 **[!UICONTROL Jump]** 旅程A中的活动。历程A是 **原始历程** 旅程B， **目标历程**.
以下是执行过程的不同步骤：

**历程A** 从外部事件触发：

1. 历程A接收与个人相关的外部事件。
1. 个人到达 **[!UICONTROL Jump]** 中。
1. 该个人将被推送到历程B，并在历程A的 **[!UICONTROL Jump]** 中。

在历程B中，第一个事件通过 **[!UICONTROL Jump]** 历程A中的活动：

1. 历程B从历程A收到内部事件。
1. 个人开始在历程B中流动。

>[!NOTE]
>
>历程B也可以通过外部事件触发。

## 最佳实践和限制

### 创作

* 的 **[!UICONTROL Jump]** 活动仅在使用命名空间的历程中可用。
* 您只能跳转到使用与原始历程相同命名空间的历程。
* 您无法跳转到以 **区段鉴别** 事件。
* 您不能具有 **[!UICONTROL Jump]** 活动和 **区段鉴别** 事件。
* 您可以包含任意数量的 **[!UICONTROL Jump]** 活动。 在 **[!UICONTROL Jump]**，则可以添加所需的任何活动。
* 您可以拥有所需数量的跳转级别。 例如，历程A跳转到历程B，跳转到历程C，等等。
* 目标历程还可以包含任意数量的 **[!UICONTROL Jump]** 活动。
* 不支持循环模式。 无法将两个或更多历程链接在一起，从而创建无限循环。 的 **[!UICONTROL Jump]** 活动配置屏幕可阻止您执行此操作。

### 执行

* 当 **[!UICONTROL Jump]** 活动时，会触发最新版本的target历程。
* 与往常一样，独特个人只能在同一历程中存在一次。 因此，如果从原始历程推送的个人已经进入目标历程，则该个人将不会进入目标历程。 不会在 **[!UICONTROL Jump]** 活动，因为这是正常行为。

## 配置跳转活动

1. 设计 **原始历程**.

   ![](../assets/jump1.png)

1. 在历程的任何步骤中，添加 **[!UICONTROL Jump]** 活动，从 **[!UICONTROL ACTIONS]** 类别。 添加标签和描述。

   ![](../assets/jump2.png)

1. 在 **Target历程** 字段。
该列表显示草稿、实时或处于测试模式的所有历程版本。 历程使用其他命名空间或以 **区段鉴别** 事件不可用。 还会过滤掉将创建循环模式的Target历程。

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >您可以单击 **Open Target历程** 图标，以在新选项卡中打开target历程。

1. 选择您要跳转到的目标历程。
的 **第一个事件** 字段中预填充了target历程第一个事件的名称。 如果您的目标历程包含多个事件，则 **[!UICONTROL Jump]** 仅允许在第一个事件上使用。

   ![](../assets/jump4.png)

1. 的 **操作参数** 部分显示目标事件的所有字段。 与其他操作类型相同，应使用源事件或数据源中的字段映射每个字段。 此信息将在运行时传递到目标历程。
1. 添加下一个活动以完成原始历程。

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >个人的身份会自动映射。 此信息在界面中不可见。

您的 **[!UICONTROL Jump]** 活动配置完成。 当您的历程处于实时模式或测试模式时，即会有人访问 **[!UICONTROL Jump]** 步骤将从推送到target历程。

当 **[!UICONTROL Jump]** 在历程中配置活动， **[!UICONTROL Jump]** 登入图标会自动添加到target历程的开头。 这有助于您识别可以从外部触发历程，也可以从 **[!UICONTROL Jump]** 活动。

![](../assets/jump7.png)

## 故障排除

当历程发布或处于测试模式时，如果出现以下情况，则会出现错误：
* target历程不再存在
* 目标历程为草稿、关闭或停止
* 如果目标历程的第一个事件发生更改，且映射被中断

![](../assets/jump6.png)
