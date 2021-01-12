---
product: adobe campaign
solution: Journey Orchestration
title: 旅程属性
description: 了解旅程属性
translation-type: tm+mt
source-git-commit: ba50a1be1a1b8665ab3c557cc1ccc5c4f27bcc87
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 1%

---


# 旅程属性 {#journey-properties}

在高级表达式编辑器中，您将在事件和数据源类别下找到&#x200B;**历程属性**&#x200B;类别。 此类别包含与给定用户档案的旅程相关的技术字段。 这是系统从实时旅程中检索到的信息，如旅程ID或遇到的特定错误。

![](../assets/journey-properties.png)

您将找到以下信息，例如：

* 旅程版本：旅程uid、旅程版本uid、实例uid等。
* 错误：数据提取、操作执行等。
* 当前步骤、最后当前步骤等。
* 丢弃的用户档案

您可以使用这些字段构建表达式。 在旅程执行过程中，将直接从旅程中检索这些值。

以下是几个使用案例的示例：

* **日志丢弃的用户档案**:您可以通过限制规则将消息中排除的所有用户档案发送到第三方系统以进行记录。为此，在超时和错误情况下设置路径，并添加条件以按特定错误类型进行筛选，例如：“通过限制规则放弃人”。 然后，您可以通过自定义操作将丢弃的用户档案推送到第三方系统。

* **发送警报以防出错**:每次消息出错时，您都可以向第三方系统发送通知。对于此，在出错时设置路径，添加条件和自定义操作。 例如，可以在Slack渠道上发送通知，并说明遇到的错误。

* **细化报告错误** :您可以根据错误类型定义条件，而不是只有一条错误消息路径。这将允许您细化报告并视图所有错误类型数据。

## 字段列表{#journey-properties-fields}

| 类别 | 字段名称 | 标签 | 说明 |
|---|---|---|------------|
| 历程版 | journeyUID | 历程标识符 |  |
|  | journeyVersionUID | 历程版本标识符 |  |
|  | journeyVersionName | 历程版本名 |  |
|  | journeyVersion描述 | 历程版本说明 |  |
|  | journeyVersion | 历程版 |  |
| 历程实例 | instanceUID | 历程实例标识符 | 实例的ID |
|  | externalKey | 外部密钥 | 触发旅程的个人标识符 |
|  | organizationId | 组织标识符 | 品牌组织 |
|  | sandboxName | 沙箱名称 | 沙箱的名称 |
| 身份 | profileId | 用户档案标识符 | 旅程中用户档案的标识符 |
|  | 命名空间 | 用户档案身份命名空间 | 旅程中命名空间的用户档案(示例：ECID) |
| 当前节点 | currentNodeId | 当前节点标识符 | 当前活动（节点）的标识符 |
|  | currentNodeName | 当前节点名称 | 当前活动（节点）的名称 |
| 上一节点 | previousNodeId | 上一节点标识符 | 上一活动（节点）的标识符 |
|  | previousNodeName | 上一节点名称 | 上一个活动（节点）的名称 |
| 错误 | lastNodeUIDInError | 错误中的最后一个节点标识符 | 错误时最新活动（节点）的标识符 |
|  | lastNodeNameInError | 错误中的最后一个节点名称 | 最新活动（节点）的名称出错 |
|  | lastNodeTypeInError | 错误中的最后一个节点类型 | 错误中最新活动（节点）的错误类型。 可能的类型：<ul><li>事件:事件、反应、SQ(例如：细分资格)</li><li>流控制：结束、条件、等待</li><li>操作：ACS操作、跳转、自定义操作</li></ul> |
|  | lastErrorCode | 上次错误代码 | 最新活动（节点）的错误代码出错。 可能的错误： <ul><li>HTTP错误代码</li><li>上限</li><li>timedOut</li><li>错误(示例：默认值，以防出现意外错误。 不应／极少发生)</li></ul> |
|  | lastExecutedActionErrorCode | 上次执行的操作错误代码 | 错误中最新操作的错误代码 |
|  | lastDataFetchErrorCode | 上次数据提取错误代码 | 从数据源获取最新数据的错误代码 |
| 时间 | lastActionExecutionElapsedTime | 上次操作执行已用时间 | 执行最新操作所花费的时间 |
|  | lastDataFetchElapsedTime | 上次数据提取已用时间 | 执行从数据源获取最新数据所花费的时间 |
