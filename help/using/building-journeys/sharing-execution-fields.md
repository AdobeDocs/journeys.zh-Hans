---
product: adobe campaign
title: journeyStep 事件操作执行字段
description: journeyStep 事件操作执行字段
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 12%

---

# journeyStep 事件操作执行字段 {#sharing-execution-fields}

此mixin将由journeyStepEvent和journeyStepProfileEvent共享。

如果步骤包含要处理的操作，则这些字段将被添加到事件有效负载中。

## actionID

正在执行的操作的ID。

类型：字符串

## actionName

操作的名称。 如果尚未设置名称，将采用stepName。

类型：字符串

## actionType

操作的类型。

类型：字符串

## actionParameterized

指示操作是否已参数化。

类型：布尔值

## actionExecutionTime

执行当前操作所用的时间（以毫秒为单位）。

类型： long

## actionExecutionError

调用操作时发生的错误类型。

类型：字符串

值：
* http
* 上限
* timeout
* error

## actionExecutionErrorCode

操作执行错误的代码。 如果错误包含代码（例如HTTP代码），则会出现。

类型：字符串

## actionExecutionOriginError

在以下两种情况下，可能会出现超时：

* 在第一次尝试时，执行操作。 在这种情况下，执行未完成，因此没有基础错误
* 重试：在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试之前尝试遇到的错误。

例如，发送电子邮件，第一次尝试时返回HTTP 500错误。 将重试获取，但2次尝试的持续时间超过了超时。 然后，该操作执行将标记为超时。 操作部分将如下所示：

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

指示操作的类型。

值：

* builtin
* ACS电子邮件
* ACS短信
* ACS推送
* 客户
* Epsilon
* ...

类型：字符串

## deliveryJobID

这将描述批处理历程的投放作业ID。

类型：字符串

## batchdeliveriyid

这将描述批处理历程的投放ID。

类型：字符串

## fromSegmentTrigger

此属性描述批处理历程是否从受众区段触发。

类型：布尔值

## actionSchedulerCount

在步骤处理期间发送到调度程序服务的调度程序通知请求的计数。

类型： long
