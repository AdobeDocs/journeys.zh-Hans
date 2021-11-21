---
product: adobe campaign
title: 历程属性
description: 了解历程属性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# 历程属性属性 {#journey-properties}

在高级表达式编辑器中，您将找到 **历程属性** 类别中，位于事件和数据源类别下。 此类别包含与给定用户档案的历程相关的技术字段。 这是系统从实时历程中检索到的信息，如历程 ID 或遇到的特定错误。

>[!NOTE]
>
>历程属性属性也在简单表达式编辑器中可用。 请参阅 [部分](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

您将找到以下信息：

* 历程版本：journey uid、journey version uid、实例uid等。
* 错误：数据获取、操作执行等。
* 当前步骤、上一当前步骤等。
* 丢弃的用户档案

您可以使用这些字段构建表达式。 在历程执行期间，将直接从历程中检索值。

以下是一些用例示例：

* **记录丢弃的用户档案**:您可以出于日志记录目的，将通过上限规则从消息中排除的所有用户档案发送到第三方系统。 为此，您需要设置超时和错误情况下的路径，并添加一个条件以过滤特定错误类型，例如：“通过设置规则上限来放弃人员”。 然后，您可以通过自定义操作将丢弃的用户档案推送到第三方系统。

* **发送警报以防出错**:每当消息发生错误时，您都可以向第三方系统发送通知。 为此，您可以设置出错路径，添加条件和自定义操作。 例如，您可以在Slack渠道上发送通知，并描述遇到的错误。

* **优化报表中的错误** :您可以根据错误类型定义条件，而不是只为出错的消息提供一个路径。 这样，您就可以优化报表并查看所有错误类型数据。

## 字段列表 {#journey-properties-fields}

| 类别 | 字段名称 | 标签 | 描述 |
|---|---|---|------------|
| 历程版本 | journeyUID | 历程标识符 |  |
|  | journeyVersionUID | 历程版本标识符 |  |
|  | journeyVersionName | 历程版本名称 |  |
|  | journeyVersionDescription | 历程版本描述 |  |
|  | journeyVersion | 历程版本 |  |
| 历程实例 | instanceUID | 历程实例标识符 | 实例的ID |
|  | externalKey | 外部键 | 触发历程的单个标识符 |
|  | organizationId | 组织标识符 | 品牌组织 |
|  | sandboxName | 沙盒名称 | 沙盒的名称 |
| 身份 | profileId | 配置文件标识符 | 历程中用户档案的标识符 |
|  | namespace | 配置文件标识命名空间 | 历程中用户档案的命名空间(示例：ECID) |
| 当前节点 | currentNodeId | 当前节点标识符 | 当前活动（节点）的标识符 |
|  | currentNodeName | 当前节点名称 | 当前活动的名称（节点） |
| 上一节点 | previousNodeId | 上一节点标识符 | 上一活动（节点）的标识符 |
|  | previousNodeName | 上一节点名称 | 上一活动的名称（节点） |
| 错误 | lastNodeUIDInError | 错误中的最后一个节点标识符 | 错误中最新活动（节点）的标识符 |
|  | lastNodeNameInError | 错误中的最后一个节点名称 | 出错的最新活动（节点）的名称 |
|  | lastNodeTypeInError | 错误中的最后一个节点类型 | 错误中最新活动（节点）的错误类型。 可能的类型：<ul><li>事件：事件、反应、SQ(示例：区段资格)</li><li>流量控制：结束，条件，等待</li><li>操作：ACS操作、跳转、自定义操作</li></ul> |
|  | lastErrorCode | 上次错误代码 | 最新活动（节点）的错误代码出错。 可能的错误： <ul><li>HTTP错误代码</li><li>上限</li><li>timedOut</li><li>错误(示例：默认值。 不应/极少发生)</li></ul> |
|  | lastExecutedActionErrorCode | 上次执行的操作错误代码 | 错误中最新操作的错误代码 |
|  | lastDataFetchErrorCode | 上次数据获取错误代码 | 从数据源获取最新数据的错误代码 |
| 时间 | lastActionExecutionElapsedTime | 上次操作执行已用时间 | 执行最新操作所花费的时间 |
|  | lastDataFetchElapsedTime | 上次数据获取已用时间 | 从数据源执行最新数据获取所花费的时间 |
