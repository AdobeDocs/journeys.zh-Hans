---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep 事件操作执行字段
description: journeyStep 事件操作执行字段
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 4%

---


# journeyStep 事件操作执行字段 {#sharing-execution-fields}

此混音将由journeyStepEvent和journeyStepProfileEvent共享。

如果步骤包含要处理的操作，则这些字段将添加到事件有效负荷。

## actionID

正在执行的操作的ID。

类型：字符串

## actionName

操作的名称。 如果未设置任何名称，则将采用stepName。

类型：字符串

## actionType

操作的类型。

类型：字符串

## actionApartemed

指示操作是否为参数化。

类型：布尔

## actionExecutionTime

执行当前操作所花费的时间（以毫秒为单位）。

类型：长

## actionExecutionError

调用操作时发生的错误类型。

类型：字符串

值：
* http
* 上限
* 超时
* 错误

## actionExecutionErrorCode

操作执行错误的代码。 如果错误包含代码（如HTTP代码），则显示。

类型：字符串

## actionExecutionOriginError

在以下两种情况下，可能会出现超时：

* 第一次尝试时，将执行一个操作。 在这种情况下，执行未完成，因此不存在基本错误
* 重试：在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试前尝试时遇到的错误。

例如，正在发送电子邮件，并在第一次尝试时返回HTTP 500错误。 将重试提取，但2次尝试的持续时间超过超时。 然后，将动作执行标记为超时。 操作部分将如下：

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

类型：字符串

## actionExecutionOriginCode

actionExecOrigError的错误代码。

类型：字符串

## actionBusinessType

指示操作类型。

值：

* 建筑
* ACS电子邮件
* ACS SMS
* ACS推送
* 客户
* Epsilon
* ...

类型：字符串

## deliveryJobID

这描述了批处理投放的历程作业ID。

类型：字符串

## batchDeliveryID

这描述了批处理投放的历程ID。

类型：字符串

## fromSegmentTrigger

此说明是否从受众区段触发批历程。

类型：布尔

## actionSchedulerCount

在步骤处理期间发送给调度程序服务的调度程序通知请求计数。

类型：长
