---
product: adobe campaign
title: journeyStep 事件数据提取字段
description: journeyStep 事件数据提取字段
feature: 历程
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 7%

---

# journeyStep 事件数据提取字段 {#sharing-fetch-fields}

此混合将由journeyStepEvent和journeyStepProfileEvent共享。

在步骤处理期间，我们可以在字段组上获取N个数据。

## fetchTotalTime

在步骤处理期间，在以毫秒为单位获取数据所花费的总时间。

类型：long

## fetchTypeInError

定义获取错误是在Adobe Experience Platform上还是在自定义数据源上。

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
* timedout
* error

## fetchErrorCode

获取错误的代码。 如果错误包含代码（如HTTP代码），则存在。 例如，如果actionExecError为http，则代码404表示HTTP 404错误。

类型：字符串

## fetchOriginError

超时可能出现以下两种情况：

* 首次尝试时，将执行该操作。 在这种情况下，执行未完成，因此不存在基本错误
* 重试时：在这种情况下，actionExecOrigError/actionExecOrigErrorCode描述在重试前尝试时遇到的错误。

例如，从统一配置文件服务获取数据，并在首次尝试时返回HTTP 500错误。 重试获取，但2次尝试的持续时间超过超时。 然后，操作执行被标记为超时。 操作部分将如下所示：

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

获取数据的次数，与源类型无关。

类型：long

## fetchPlatformTotalTime

从Adobe Experience Platform（以米为单位）获取数据所花费的总时间。 备注：从引擎向扩充服务发送扩充事件并接收响应的时间开始计算此时间量。

类型：long

## fetchPlatformCount

从Adobe Experience Platform获取数据的次数。

类型：long

## fetchCustomTotalTime

以millis为单位获取自定义数据的时长。 备注：从引擎向扩充服务发送扩充事件并接收响应的时间开始计算此时间量

类型：long

## fetchCustomCount

从外部系统获取自定义数据的次数。

类型：long
