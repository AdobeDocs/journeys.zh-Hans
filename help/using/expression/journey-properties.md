---
product: adobe campaign
title: 历程属性
description: 了解历程属性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 3%

---

# 历程属性属性 {#journey-properties}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


在高级表达式编辑器中，您将在事件和数据源类别下找到&#x200B;**历程属性**&#x200B;类别。 此类别包含与给定用户档案的历程相关的技术字段。 这是系统从实时历程中检索到的信息，例如历程ID或遇到的特定错误。

>[!NOTE]
>
>简单表达式编辑器中也提供历程属性。 请参阅此[章节](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

例如，您将找到有关以下内容的信息：

* 历程版本：历程uid、历程版本uid、实例uid等。
* 错误：数据提取、操作执行等。
* 当前步骤、上一个当前步骤等。
* 已丢弃的配置文件

您可以使用这些字段构建表达式。 在历程执行期间，将直接从历程中检索值。

以下是一些用例示例：

* **记录丢弃的用户档案**：您可以将从消息中排除的所有用户档案按照上限规则发送到第三方系统以进行记录。 为此，您可以设置超时和错误时的路径，并添加条件以筛选特定错误类型，例如“通过设置规则上限来放弃人员”。 然后，您可以通过自定义操作将已丢弃的用户档案推送到第三方系统。

* **发生错误时发送警报**：每次消息发生错误时，您都可以向第三方系统发送通知。 为此，您可以设置路径以防出错，还可以添加条件和自定义操作。 例如，您可以通过Slack渠道发送包含所遇到错误说明的通知。

* **优化报表中的错误** ：您可以为每个错误类型定义条件，而不是让出错的消息只有一个路径。 这将允许您优化报告并查看所有错误类型数据。

## 字段列表 {#journey-properties-fields}

| 类别 | 字段名称 | 标签 | 描述 |
|---|---|---|------------|
| 历程版本 | journeyUID | 历程标识符 | |
| | journeyVersionUID | 历程版本标识符 | |
| | journeyVersionName | 历程版本名称 | |
| | journeyVersionDescription | 历程版本描述 | |
| | journeyVersion | 历程版本 | |
| 历程实例 | instanceUID | 历程实例标识符 | 实例的ID |
| | externalkey | 外部密钥 | 触发历程的单个标识符 |
| | organizationId | 组织标识符 | 品牌组织 |
| | sandboxName | 沙盒名称 | 沙盒的名称 |
| 身份标识 | profileId | 配置文件身份标识符 | 历程中用户档案的标识符 |
| | 命名空间 | 配置文件身份命名空间 | 历程中配置文件的命名空间（示例：ECID） |
| 当前节点 | currentNodeId | 当前节点标识符 | 当前活动（节点）的标识符 |
| | currentNodeName | 当前节点名称 | 当前活动的名称（节点） |
| 上一个节点 | previousNodeId | 上一节点标识符 | 上一个活动（节点）的标识符 |
| | previousNodeName | 上一个节点名称 | 上一个活动的名称（节点） |
| 错误 | lastNodeUIDInError | 上一出错的节点标识符 | 出错的最新活动（节点）的标识符 |
| | lastNodeNameInError | 上一出错的节点名称 | 出错的最新活动（节点）的名称 |
| | lastNodeTypeInError | 上一出错的节点类型 | 出错的最新活动（节点）的错误类型。 可能的类型：<ul><li>事件：事件、反应、SQ（示例：区段鉴别）</li><li>流量控制：结束、条件、等待</li><li>操作：ACS操作、跳转、自定义操作</li></ul> |
| | lastErrorcode | 上一错误代码 | 最新活动（节点）的错误代码出错。 可能的错误： <ul><li>HTTP错误代码</li><li>上限</li><li>timedout</li><li>错误(示例：发生意外错误时的默认值。 不应该/极少数发生)</li></ul> |
| | lastExecutedActionErrorCode | 上次执行的操作产生的错误代码 | 最新出错操作的错误代码 |
| | lastDataFetchErrorCode | 上次数据获取产生的错误代码 | 从数据源获取最新数据的错误代码 |
| 时间 | lastActionExecutionElapsedTime | 执行上一个操作占用的时间 | 执行最新操作所花费的时间 |
| | lastDataFetchElapsedTime | 上次获取数据占用的时间 | 执行从数据源获取的最新数据所花费的时间 |
