---
product: adobe campaign
title: journeyStep 事件数据提取字段
description: journeyStep 事件数据提取字段
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 4%

---

# journeyStep 事件数据提取字段 {#sharing-fetch-fields}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


此mixin将由journeyStepEvent和journeyStepProfileEvent共享。

在步骤处理期间，我们可以在字段组上获取N个数据。

## fetchTotaltime

在步骤处理期间进行数据提取所花费的总时间（以毫秒为单位）。

类型： long

## fetchTypeInError

定义错误获取是在Adobe Experience Platform上还是在自定义数据源上。

类型：字符串

值：
* aep
* 自定义

## fetchError

处理数据获取时发生的错误类型。

类型：字符串

值：
* http
* 上限
* 超时
* 错误

## fetchErrorCode

获取错误的代码。 如果错误包含代码（如HTTP代码），则显示。 例如，如果actionExecError为http，则代码404表示HTTP 404错误。

类型：字符串

## fetchOriginError

在以下两种情况下，可能会出现超时：

* 在第一次尝试时，将执行该操作。 在这种情况下，执行未完成，因此不存在基础错误
* 重试：在这种情况下，actionExecOrigError/actionExecOrigErrorCode将描述在重试之前尝试时遇到的错误。

例如，正在从统一配置文件服务中获取数据，并且在第一次尝试时返回HTTP 500错误。 将重试获取，但两次尝试的持续时间超过了超时。 然后，操作执行将标记为超时。 操作部分将如下所示：

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

获取数据的次数，不考虑源的类型。

类型： long

## fetchPlatformTotaltime

从Adobe Experience Platform获取数据所需的总时间（以millis为单位）。 备注：此时间量从引擎将扩充事件发送到扩充服务并接收响应时开始计算。

类型： long

## Fetchplatformcount

从Adobe Experience Platform获取数据的次数。

类型： long

## fetchCustomTotalTime

获取自定义数据的时间（以毫秒为单位）。 备注：此时间量从引擎将扩充事件发送到扩充服务并接收响应时开始计算

类型： long

## Fetchcustomcount

从外部系统获取自定义数据的次数。

类型： long
