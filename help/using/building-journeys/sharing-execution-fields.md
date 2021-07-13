---
product: adobe campaign
title: journeyStep 事件操作执行字段
description: journeyStep 事件操作执行字段
feature: 历程
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 13%

---

# journeyStep 事件操作执行字段 {#sharing-execution-fields}

此混合将由journeyStepEvent和journeyStepProfileEvent共享。

如果步骤包含要处理的操作，则这些字段将添加到事件有效负载中。

## actionID

正在执行的操作的ID。

类型：字符串

## actionName

操作的名称。 如果未设置名称，则将执行stepName。

类型：字符串

## actionType

操作的类型。

类型：字符串

## actionParameted

指示操作是否已参数化。

类型：布尔值

## actionExecutionTime

执行当前操作所花费的时间（以毫秒为单位）。

类型：long

## actionExecutionError

调用操作时发生的错误类型。

类型：字符串

值：
* http
* 上限
* timeout
* error

## actionExecutionErrorCode

操作执行错误的代码。 如果错误包含代码（如HTTP代码），则存在。

类型：字符串

## actionExecutionOriginError

超时可能出现以下两种情况：

* 首次尝试时，将执行操作。 在这种情况下，执行未完成，因此不存在基本错误
* 重试时：在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试前尝试时遇到的错误。

例如，正在发送电子邮件，并在首次尝试时返回HTTP 500错误。 重试获取，但2次尝试的持续时间超过超时。 然后，操作执行被标记为超时。 操作部分将如下所示：

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

* 建筑物
* ACS电子邮件
* ACS SMS
* ACS推送
* 客户
* Epsilon
* ...

类型：字符串

## deliveryJobID

这描述了批处理历程的提交作业ID。

类型：字符串

## batchDeliveryID

此变量描述批处理历程的提交ID。

类型：字符串

## fromSegmentTrigger

此描述是否从受众区段触发批量历程。

类型：布尔值

## actionSchedulerCount

在步骤处理期间发送到调度程序服务的调度程序通知请求计数。

类型：long
