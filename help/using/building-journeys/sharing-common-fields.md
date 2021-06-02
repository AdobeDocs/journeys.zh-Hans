---
product: adobe campaign
title: journeysteps事件常用字段
description: journeysteps事件常用字段
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# journeysteps事件常用字段{#sharing-common-fields}

此混合将由journeyStepEvent和journeyStepProfileEvent共享。

这些是[!DNL Journey Orchestration]发送到Adobe Experience Platform的常用XDM字段。 对于历程中处理的每个步骤，都将发送通用字段。 自定义操作和扩充使用更多特定字段。

其中某些字段仅在特定处理模式（操作执行、数据获取等）中可用 以限制事件的大小。

## 入口

指示用户是否已进入历程。 如果不存在，则我们假定该值为false。

类型：布尔

值：true/false

## 重入

指示用户是否使用同一实例重新进入历程。 如果不存在，则我们假定该值为false。

类型：布尔

值：true/false

## instanceEnded

指示实例是否已结束（成功或未成功）。

类型：布尔

## eventID

处理中的事件ID，用于步骤处理。 如果事件是外部事件，则值为其eventId。 如果事件是内部事件，则值为内部eventId（例如scheduledNotificationReceived、exceutedAction等）。

类型：字符串

## nodeID

客户端节点id（从画布中）。

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

可能值：

* 条件
* 操作
* 调度程序
* 计时器

## stepStatus

完成处理（触发步骤事件）后，步骤的状态，表示步骤的状态。

类型：字符串

状态可以是：

* 结束：该步骤没有过渡，且其处理已成功结束。
* 错误：步骤处理引发错误。
* 过渡：该步骤正在等待事件转换到另一个步骤。
* 上限：在操作或扩充期间引发的上限错误导致步骤失败。
* timedout:在操作或扩充过程中引发的超时错误导致步骤失败。
* instanceTimedout:该步骤已停止处理，因为实例已达到其超时。

## journeyID

历程的ID。

类型：字符串

## journeyVersionID

历程版本的ID。 此ID表示对历程的身份引用，对于journeyStepEvent。

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

## externalKey

从事件提取的外部键值以处理它。

类型：字符串

## parentStepID

实例中当前已处理步骤的父级的步骤ID。

类型：字符串

## parentStepName

当前步骤的父项的步骤名称。

类型：字符串

## parentTransitionID

将实例引入已处理步骤的过渡的ID。

类型：字符串

## parentTransitionName

将实例引入已处理步骤的过渡的名称。

类型：字符串

## inTest

指示此历程是否处于测试模式。

类型：布尔

## processingTime

从实例步骤进入到处理结束的总时间（以毫秒为单位）。

类型：long

## instanceType

指示实例类型（如果是批类型或单一类型）。

类型：字符串

值：批次/单一

## recurrenceIndex

当历程是批处理并且是定期的时，循环的索引（首次运行的recurrenceIndex = 1）。

类型：long

## isBatchToUnimation

指示此单一实例是否已从批处理实例触发。

类型：布尔

## batchExternalKey

批处理事件的外部键。

类型：字符串

## batchInstanceID

这是批量实例ID。

类型：字符串

## batchUneminaryBranchID

如果实例是从批处理实例触发的，则表示唯一的分支ID。

类型：字符串
