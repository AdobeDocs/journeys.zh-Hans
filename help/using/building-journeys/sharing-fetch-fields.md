---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep 事件数据提取字段
description: journeyStep 事件数据提取字段
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 4%

---


# journeyStep 事件数据提取字段 {#sharing-fetch-fields}

此混音将由journeyStepEvent和journeyStepProfileEvent共享。

在步骤处理期间，我们可以在字段组上获取N个数据。

## fetchTotalTime

在步骤处理期间，在以毫秒为单位的数据提取中花费的总时间。

类型：长

## fetchTypeInError

定义提取错误是在Adobe Experience Platform上还是在自定义数据源上。

类型：字符串

值：
* aep
* 自定义

## fetchError

处理数据提取时发生的错误类型。

类型：字符串

值：
* http
* 上限
* timedout
* 错误

## fetchErrorCode

提取错误的代码。 如果错误包含代码（如HTTP代码），则显示。 例如，如果actionExecError是http，则代码404表示HTTP 404错误。

类型：字符串

## fetchOriginError

在以下两种情况下，可能会出现超时：

* 在第一次尝试时，将执行该操作。 在这种情况下，执行未完成，因此不存在基本错误
* 重试：在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试前尝试时遇到的错误。

例如，正在从统一用户档案服务中获取数据，第一次尝试时会返回HTTP 500错误。 将重试提取，但2次尝试的持续时间超过超时。 然后，将动作执行标记为超时。 操作部分将如下：

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

类型：字符串

## fetchOriginErrorCode

系统[!DNL Journey Orchestration]提供的错误代码正在查询。 例如，它可以是404、500等。

类型：字符串

## fetchCount

获取数据的次数，而不管源的类型。

类型：长

## fetchPlatformTotalTime

从Adobe Experience Platform获取数据所花费的总时间（以百万计）。 备注：从引擎将扩充事件发送到扩充服务并接收响应的时间计算该时间量。

类型：长

## fetchPlatformCount

从Adobe Experience Platform获取数据的次数。

类型：长

## fetchCustomTotalTime

以毫秒为单位提取自定义数据的时间。 备注：从引擎将扩充事件发送到扩充服务并接收响应的时间计算该时间量

类型：长

## fetchCustomCount

从外部系统获取自定义数据的次数。

类型：长
