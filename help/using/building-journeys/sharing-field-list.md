---
title: 步骤事件字段列表
description: 步骤事件字段列表
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 16%

---

# 步骤事件字段列表 {#sharing-field-list}

步骤事件字段按类别进行组织。

* 调试信息字段
* 历程字段
* 用户档案字段
* 服务事件字段

## debugInfo

| 字段名称 | 类型 | 描述 |
|---|---|------------|
| requestId | 字符串 | Journey Orchestration用于跟踪请求流的请求ID。 |

## 历程

此字段组用在历程架构中（与journeyStepEvent相关）。 它包含以下字段：

| 字段名称 | 类型 | 描述 |
|---|---|------------|
| ID | 字符串 | 给定历程的标识符 |
| 版本ID | 字符串 | 历程版本的ID。 此id表示历程的标识 |
| name | 字符串 | 历程的名称 |
| 描述 | 字符串 | 历程描述 |
| 版本 | 字符串 | 版本，表示为 `major`.`minor` |

## 个人资料

此字段组特定于journeyStepEvent:此事件与历程相关，并且没有identityMap，用于描述用户档案身份（如果有）。

对于journeyStepEvent，我们还需要添加与标识相关的字段：

| 字段名称 | 类型 | 描述 |
|---|---|------------|
| ID | 字符串 | 用户档案标识符用于标识在历程中发送/使用的用户档案。 例如：foo@adobe.com。 |
| namespace | 字符串 | 此字段描述在历程中使用的配置文件引用的命名空间。 例如：电子邮件、ECID |

## serviceEvents

此混合包含与用户档案导出作业对应的所有字段。

| 字段名称 | 类型 | 描述 |
|---|---|------------|
| ID | 字符串 | 触发的区段导出作业的标识符 |
| 状态 | 字符串 | 区段导出作业的状态：已排队，已启动，已完成 |
| exportCountTotal | 整数 | 区段导出作业的最大可能值 |
| exportCountReatived | 整数 | 通过作业导出的区段的实际数量 |
| exportCountFailed | 整数 | 通过作业导出时，区段数失败 |
| exportSegmentID | 字符串 | 要导出的区段的标识符 |
| eventType | 字符串 | 事件类型，用于指示它是否为信息事件的错误事件：信息，错误 |
| eventCode | 字符串 | 指示相应eventType原因的错误代码 |

## stepEvents

此类别包含原始步骤事件字段。 请参阅 [部分](../building-journeys/sharing-legacy-fields.md).
