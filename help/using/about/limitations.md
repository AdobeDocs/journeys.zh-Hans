---
product: adobe campaign
title: Journey Orchestration限制
description: 了解有关Journey Orchestration限制的更多信息
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 51%

---

# 限制 {#limitations}

以下是与Journey Orchestration的使用相关的限制。

## 一般历程护栏 {#journeys-guardrails-journeys}

* 历程中的活动数量限制为 50 个。活动数显示在历程画布的左上角部分。
* 一个组织中的&#x200B;**实时历程**&#x200B;数量限制为每个沙盒 100 个。达到此限制后，您将无法再发布新历程。

## 常规操作限制

* 如果出现错误，系统将执行三次重试。无法根据收到的错误消息调整重试次数。 
* 内置 **反应** 事件允许您对开箱即用的操作做出反应(请参阅此 [页面](../building-journeys/reaction-events.md))。 如果要对通过自定义操作发送的消息做出反应，则需要配置专用事件。 

## 历程版本限制 {#journey-versions-limitations}

* v1 中以事件活动开始的历程，在后续版本中无法以事件之外的其他内容开始。无法以&#x200B;**区段资格**&#x200B;事件开始历程。
* v1 中以&#x200B;**区段资格**&#x200B;活动开始的历程在后续版本中必须始终以&#x200B;**区段资格**&#x200B;开始。
* 在中选择的区段和命名空间 **区段鉴别** （第一个节点）无法在新版本中更改。
* 在所有历程版本中，重新进入规则必须相同。

## 区段鉴别 {#segment-qualification}

* 此 **区段鉴别** 由于吞吐量限制，活动不能与Adobe Campaign Standard事务型消息传递结合使用。 请参阅 [Adobe Campaign Standard产品描述](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 
## 自定义操作限制

* 自定义操作 URL 不支持动态参数。 
* 仅支持 POST 和 PUT 调用方法. 
* 查询参数或标头的名称不得以“.”或“$”开始。 
* 不允许使用 IP 地址. 
* 不允许使用内部 Adobe 地址 (.adobe.)。 
## Adobe Campaign操作限制

* 对于给定实例，Adobe Campaign Standard事务性消息传递在各个渠道上的规模为每小时最多50,000条消息。 请参阅 [Adobe Campaign Standard产品描述](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 
## 事件限制

* 对于系统生成的事件，必须先在Journey Orchestration中配置用于启动客户历程的流数据，才能获取唯一的编排ID。 此编排ID必须附加到传入Adobe Experience Platform的流有效负载中。 此限制不适用于基于规则的事件。 
## 数据源限制

* 可在客户历程中利用外部数据源实时查找外部数据。 这些源必须可通过REST API使用，支持JSON，并能够处理大量请求。

## 在创建配置文件的同时开始的历程 {#journeys-limitation-profile-creation}

在 Adobe Experience Platform 中，创建/更新基于 API 的配置文件存在延迟。延迟方面的服务水平目标 (SLT) 是在每秒请求量 (RPS) 为 20K 的情况下，从摄取到统一配置文件的第 95% 的请求的延迟小于 1 分钟。

如果在创建用户档案的同时触发了历程，并立即检查/检索用户档案服务中的信息，则该事件可能无法正常工作。

您可以从以下两种解决方案中选择一种：

* 在第一个事件后添加等待活动，以便给 Adobe Experience Platform 提供向用户档案服务执行摄取所需的时间。

* 设置不会立即利用用户档案的历程。例如，如果历程旨在确认帐户创建，则体验事件可能包含发送第一条确认消息（名字、姓氏、电子邮件地址等）所需的信息。
