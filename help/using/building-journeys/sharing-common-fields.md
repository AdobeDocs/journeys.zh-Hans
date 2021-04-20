---
product: adobe campaign
solution: Journey Orchestration
title: 工作步骤事件公用字段
description: 工作步骤事件公用字段
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# journeysteps事件公用字段{#sharing-common-fields}

此混音将由journeyStepEvent和journeyStepProfileEvent共享。

这些是[!DNL Journey Orchestration]发送到Adobe Experience Platform的常见XDM字段。 在旅程中处理的每个步骤都会发送通用字段。 自定义操作和扩充使用更多特定字段。

其中有些字段仅在特定处理模式（操作执行、数据提取等）中可用 以限制事件的大小。

## 入口

指示用户是否已进入旅程。 如果不存在，则假定该值为false。

类型：布尔

值：true/false

## 重新入场

指示用户是否已使用同一实例重新进入旅程。 如果不存在，则假定该值为false。

类型：布尔

值：true/false

## instanceEnded

指示实例是否已结束（成功或未成功）。

类型：布尔

## eventID

事件ID在处理中，用于步骤处理。 如果事件是外部的，则值为其eventId。 如果事件是内部事件，则该值为内部事件ID（如scheduledNotificationReceived、excurededAction等）。

类型：字符串

## nodeID

客户端节点ID（从画布中）。

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

## stepStatus

完成处理(和触发步骤事件)时步骤的状态，表示步骤的状态。

类型：字符串

状态可以是：

* 结束：该步骤没有过渡，且其处理已成功结束。
* 错误：步骤处理引发错误。
* 过渡:该步骤正在等待事件过渡到另一步骤。
* capped:在操作或扩充期间触发的封闭错误上，该步骤失败。
* timedout:该步骤在超时错误(在操作或扩充期间引发)时失败。
* instanceTimedout:该步骤已停止其处理，因为实例已达到其超时。

## journeyID

旅程的ID。

类型：字符串

## journeyVersionID

旅程版本的ID。 此id表示对旅程的标识引用，对于journeyStepEvent。

类型：字符串

## journeyVersionName

旅程版本的名称。

类型：字符串

## journeyVersion

旅程版本。

类型：字符串

## instanceID

旅程实例的内部ID。

类型：字符串

## externalKey

从事件提取的外部密钥以处理它。

类型：字符串

## parentStepID

实例中当前已处理步骤的父项的步骤ID。

类型：字符串

## parentStepName

当前步骤的父项的步骤名称。

类型：字符串

## parentTransitionID

已将实例带到处理步骤的过渡的ID。

类型：字符串

## parentTransitionName

将实例带到处理步骤的过渡的名称。

类型：字符串

## inTest

指示此旅程是否处于测试模式。

类型：布尔

## processingTime

从实例步骤入口到处理结束的总时间（以毫秒为单位）。

类型：长

## instanceType

指示实例类型（如果是批或单一）。

类型：字符串

值：批/酉

## recurrenceIndex

当旅程为批次并循环时（第一次运行的recurrenceIndex = 1）的循环索引。

类型：长

## isBatchToUnimation

指示此单一实例是否已从批处理实例触发。

类型：布尔

## batchExternalKey

用于批次事件的外部键。

类型：字符串

## batchInstanceID

这是批处理实例ID。

类型：字符串

## batchUnimaryBranchID

如果该实例是从批处理实例触发的，则为酉分支ID。

类型：字符串
