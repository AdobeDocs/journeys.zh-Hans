---
title: journeyStep事件数据提取字段
description: journeyStep事件数据提取字段
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# journeyStep事件数据提取字段 {#sharing-fetch-fields}

此混音将由journeyStepEvent和journeyStepProfileEvent共享。

在步骤处理过程中，我们可以在字段组上获取N个数据。

## fetchTotalTime

在步骤处理过程中，以毫秒为单位的数据提取总时间。

类型： 长

## fetchTypeInError

定义提取错误是在Adobe Experience Platform上还是在自定义数据源上。

类型： 字符串

值：
* aep
* 自定义

## fetchError

处理数据提取时发生的错误类型。

类型： 字符串

值：
* http
* 上限
* timedout
* 错误

## fetchErrorCode

提取错误的代码。 如果错误包含代码（如HTTP代码），则显示。 例如，如果actionExecError是http，则代码404表示HTTP 404错误。

类型： 字符串

## fetchOriginError

超时可能发生，有两种情况：

* 第一次尝试时，将执行该操作。 在这种情况下，执行未完成，因此不存在基本错误
* 重试： 在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试前在尝试时遇到的错误。

例如，从统一用户档案服务获取数据，并在第一次尝试时返回HTTP 500错误。 将重试提取，但2次尝试的持续时间超过超时。 然后，将操作执行标记为时间结束。 操作部分将如下所示：

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

类型： 字符串

## fetchOriginErrorCode

系统提供的错误代码 [!DNL Journey Orchestration] 正在查询。 例如，它可以是404、500等。

类型： 字符串

## fetchCount

无论源的类型如何，获取数据的次数都是多少。

类型： 长

## fetchPlatformTotalTime

从Adobe Experience Platform获取数据所花费的总时间（以百万计）。 注释： 从引擎将扩充事件发送到扩充服务并接收响应的时间开始计算该时间量。

类型： 长

## fetchPlatformCount

从Adobe Experience Platform获取数据的次数。

类型： 长

## fetchCustomTotalTime

以毫秒为单位提取自定义数据的时间。 注释： 从引擎将扩充事件发送到扩充服务并接收响应的时间开始计算该时间量

类型： 长

## fetchCustomCount

从外部系统获取自定义数据的次数。

类型： 长
