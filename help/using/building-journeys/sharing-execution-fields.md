---
title: 旅程步骤事件操作执行字段
description: 旅程步骤事件操作执行字段
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
source-wordcount: '320'
ht-degree: 0%

---


# 旅程步骤事件操作执行字段 {#sharing-execution-fields}

此混音将由journeyStepEvent和journeyStepProfileEvent共享。

如果该步骤包含要处理的操作，则这些字段将添加到事件有效负荷。

## actionID

正在执行的操作的ID。

类型： 字符串

## actionName

操作的名称。 如果未设置任何名称，将采用stepName。

类型： 字符串

## actionType

操作的类型。

类型： 字符串

## actionAparameterized

指示操作是否为参数化。

类型： 布尔

## actionExecutionTime

执行当前操作所花费的时间（以毫秒为单位）。

类型： 长

## actionExecutionError

调用操作时发生的错误类型。

类型： 字符串

值：
* http
* 上限
* 超时
* 错误

## actionExecutionErrorCode

操作执行错误的代码。 如果错误包含代码（如HTTP代码），则显示。

类型： 字符串

## actionExecutionOriginError

超时可能发生，有两种情况：

* 第一次尝试时，将执行操作。 在这种情况下，执行未完成，因此不存在基本错误
* 重试： 在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试前在尝试时遇到的错误。

例如，正在发送电子邮件，并在第一次尝试时返回HTTP 500错误。 将重试提取，但2次尝试的持续时间超过超时。 然后，将操作执行标记为时间结束。 操作部分将如下所示：

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

类型： 字符串

## actionExecutionOriginCode

actionExecOrigError的错误代码。

类型： 字符串

## actionBusinessType

指示操作类型。

值：

* 建筑
* ACS电子邮件
* ACS SMS
* ACS推送
* 客户
* ε
* ...

类型： 字符串

## deliveryJobID

这描述了批旅程的投放作业ID。

类型： 字符串

## batchDeliveryID

这描述了批旅程的投放ID。

类型： 字符串

## fromSegmentTrigger

此说明是否从受众段触发批旅程。

类型： 布尔

## actionSchedulerCount

在步骤处理过程中发送给调度程序服务的调度程序通知请求计数。

类型： 长
