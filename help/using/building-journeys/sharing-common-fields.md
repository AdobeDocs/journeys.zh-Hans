---
title: 旅程事件常用字段
description: 旅程事件常用字段
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---


# 旅程事件常用字段 {#sharing-common-fields}

此混音将由journeyStepEvent和journeyStepProfileEvent共享。

这些是旅程编排发送给Adobe数据平台的常见XDM字段。 在旅程中处理的每个步骤都会发送通用字段。 更多特定字段用于自定义操作和扩充。

其中有些字段仅在特定处理模式（操作执行、数据提取等）中可用 以限制事件的大小。

## 入口

指示用户是否已进入旅程。 如果不存在，则假定该值为false。

类型： 布尔

值： true/false

## 重新入口

指示用户是否已使用同一实例重新输入旅程。 如果不存在，则假定该值为false。

类型： 布尔

值： true/false

## instanceEnded

指示实例是否已结束（成功或未成功）。

类型： 布尔

## eventID

事件ID在处理中，用于步骤处理。 如果事件是外部的，则值为其eventId。 如果事件是内部事件ID，则此值为内部事件ID（如scheduledNotificationReceived、executedAction等）。

类型： 字符串

## nodeID

客户端节点id（从画布中）。

类型： 字符串

## stepID

当前正在处理的步骤的唯一id。

类型： 字符串

## stepName

当前正在处理的步骤的名称。

类型： 字符串

## stepType

步骤的类型。

类型： 字符串

可能的值：

* 条件
* 操作
* 调度程序
* 计时器

## stepStatus

完成处理时(以及触发步骤事件)步骤的状态，表示步骤的状态。

类型： 字符串

状态可以是：

* 结束： 该步骤没有过渡，且其处理已成功结束。
* 错误： 步骤处理已引发错误。
* 过渡: 该步骤正在等待事件过渡到另一步骤。
* capped: 在操作或扩充期间，该步骤在限制错误上失败。
* timedout: 该步骤在超时错误时失败，在操作或扩充期间引发。
* instanceTimedout: 该步骤已停止其处理，因为实例已达到其超时。

## journeyID

旅程的ID。

类型： 字符串

## journeyVersionID

旅程版本的ID。 对于journeyStepEvent，此id表示对旅程的标识引用。

类型： 字符串

## journeyVersionName

旅程版本的名称。

类型： 字符串

## journeyVersion

旅程版本。

类型： 字符串

## 实例ID

旅程实例的内部ID。

类型： 字符串

## externalKey

从事件提取的外部密钥进行处理。

类型： 字符串

## parentStepID

实例中当前已处理步骤的父项的步骤ID。

类型： 字符串

## parentStepName

当前步骤的父项的步骤名称。

类型： 字符串

## parentTransitionID

将实例带到已处理步骤的过渡的ID。

类型： 字符串

## parentTransitionName

将实例带到已处理步骤的过渡的名称。

类型： 字符串

## inTest

指示此旅程是否处于测试模式。

类型： 布尔

## processingTime

从实例步骤入口到处理结束的总时间（以毫秒为单位）。

类型： 长

## instanceType

指示实例类型（如果为批或酉）。

类型： 字符串

值： 批／酉

## recurrenceIndex

当旅程为批处理并重复时的重复的索引（第一次运行的recurrenceIndex = 1）。

类型： 长

## isBatchToUnigany

指示此单一实例是否已从批处理实例触发。

类型： 布尔

## batchExternalKey

外部批次事件键。

类型： 字符串

## batchInstanceID

这是批处理实例ID。

类型： 字符串

## batchUnignalBranchID

如果实例是从批处理实例（酉分支ID）触发的。

类型： 字符串
