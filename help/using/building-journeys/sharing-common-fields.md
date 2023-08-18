---
product: adobe campaign
title: journeysteps事件常用字段
description: journeysteps事件常用字段
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# journeysteps事件常用字段 {#sharing-common-fields}

此mixin将由journeyStepEvent和journeyStepProfileEvent共享。

以下是常见的XDM字段 [!DNL Journey Orchestration] 发送至Adobe Experience Platform。 对于历程中处理的每个步骤，都将发送公共字段。 更具体的字段用于自定义操作和增强。

其中某些字段仅在特定处理模式（操作执行、数据获取等）中可用 以限制事件大小。

## 入口

指示用户是否已进入历程。 如果不存在，我们假定值为false。

类型：布尔值

值： true/false

## 重入

指示用户是否已重新进入具有相同实例的历程。 如果不存在，我们假定值为false。

类型：布尔值

值： true/false

## instanceEnded

指示实例是否已结束（成功或失败）。

类型：布尔值

## eventID

处理中的事件ID，用于步骤处理。 如果事件是外部事件，则该值为其eventId。 如果事件是内部事件，则该值为内部eventId（例如scheduledNotificationReceived、executedAction等）。

类型：字符串

## nodeID

客户端节点ID（来自画布）。

类型：字符串

## stepID

当前正在处理的步骤的唯一ID。

类型：字符串

## stepName

当前正在处理的步骤的名称。

类型：字符串

## stepType

步骤的类型。

类型：字符串

可能的值：

* 条件
* 操作
* 调度程序
* 计时器

## 步骤状态

步骤的状态，表示步骤在处理完成（并触发步骤事件）时的状态。

类型：字符串

状态可以是：

* 已结束：步骤没有过渡，其处理已成功结束。
* 错误：步骤处理引发错误。
* 过渡：步骤正在等待事件过渡到另一个步骤。
* capped：步骤因操作或扩充期间引发的上限错误而失败。
* 超时：步骤因超时错误而失败，该错误在操作或扩充期间引发。
* instanceTimedout：步骤已停止处理，因为实例已达到超时。

## journeyID

历程的ID。

类型：字符串

## journeyVersionID

历程版本的ID。 在journeyStepEvent的情况下，此id表示对历程的标识引用。

类型：字符串

## journeyVersionName

历程版本的名称。

类型：字符串

## journeyVersion

历程版本的版本。

类型：字符串

## instanceID

历程实例的内部ID。

类型：字符串

## externalkey

从事件提取外部键以对其进行处理。

类型：字符串

## parentstepid

实例中当前已处理步骤的父步骤ID。

类型：字符串

## parentStepName

当前步骤的父级步骤名称。

类型：字符串

## parentTransitionID

将实例带到已处理步骤的过渡的ID。

类型：字符串

## parentTransitionName

将实例带到已处理步骤的过渡的名称。

类型：字符串

## inTest

指示此历程是否处于测试模式。

类型：布尔值

## processingTime

从实例步骤进入到处理结束的总时间（以毫秒为单位）。

类型： long

## instancetype

指示实例类型（批处理或单一实例）。

类型：字符串

值：批处理/单一

## recurrenceIndex

如果历程是批处理周期性的（第一次运行具有recurrenceIndex = 1），则为循环的索引。

类型： long

## isBatchToUniary

指示此单一实例是否已从批处理实例触发。

类型：布尔值

## batchExternalKey

批次事件的外部键。

类型：字符串

## batchinstanceid

这是批次实例ID。

类型：字符串

## batchUnitaryBranchID

如果实例是从批处理实例触发的，则为单一分支ID。

类型：字符串
