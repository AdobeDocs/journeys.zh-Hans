---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration限制
description: 了解有关Journey Orchestration限制的更多信息
translation-type: tm+mt
source-git-commit: 1433ccabaceb31c7ffac117a31531d0d380a54f8
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 2%

---


# 限制{#limitations}

以下是与使用Journey Orchestration相关的限制。

## 一般操作限制

* 没有发送限制。 
* 在发生错误时系统地执行两个重试。 无法根据收到的错误消息调整重试数。 
* 内置的&#x200B;**Reaction**&#x200B;事件允许您对现成操作做出响应（请参阅此[页面](../building-journeys/reaction-events.md)）。 如果您要对通过自定义操作发送的消息做出响应，则需要配置专用事件。 
* 不存在按产品分类的Adobe Campaign Classic集成。

## 历程版本限制{#journey-versions-limitations}

* 从v1中的事件活动开始的旅程不能与其他版本中的事件开始。 您不能开始具有&#x200B;**区段资格**&#x200B;事件的旅程。
* 从v1中的&#x200B;**区段资格**&#x200B;活动开始的旅程必须始终与其他版本中的&#x200B;**区段资格**&#x200B;开始。
* 在&#x200B;**区段资格**（第一个节点）中选择的区段和命名空间在新版本中无法更改。
* 在所有旅程版本中，重新进入规则必须相同。

## 区段资格{#segment-qualification}

* 由于吞吐量限制，**区段资格**&#x200B;活动不能与Adobe Campaign Standard Transactional Messaging一起使用。 请参阅[Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 自定义操作限制

* 自定义操作URL不支持动态参数。 
* 仅支持POST和PUT调用方法。 
* 查询参数或头的名称不能与“。”开始 或者 &quot;$&quot;. 
* 不允许使用IP地址。 
* 内部Adobe地址(.adobe.) 不允许。
 

## Adobe Campaign操作限制

* Adobe Campaign Standard Transactional Messaging在给定实例的渠道中每小时最多有50 000条消息。 请参阅[Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 事件限制

* 对于系统生成的事件，用于启动客户旅程的流数据必须首先在Journey Orchestration中配置，才能获得唯一的业务流程ID。 此业务流程ID必须附加到传入Adobe Experience Platform的流负载。 此限制不适用于基于规则的事件。
 

## 数据源限制

* 在客户旅程中可利用外部数据源实时查找外部数据。 这些源必须可通过REST API使用，支持JSON并能够处理大量请求。

## 历程与用户档案创建同时启动{#journeys-limitation-profile-creation}

在Adobe Experience Platform中创建/更新基于API的用户档案时存在延迟。 服务级别目标(SLT)在从摄取到统一用户档案(每秒20K请求数(RPS))的95%请求时，延迟小于1分钟。

如果历程同时触发到用户档案创建并立即检查/检索用户档案服务中的信息，则它可能无法正常工作。

您可以从以下两种解决方案中进行选择：

* 在第一个事件后添加等待活动，为Adobe Experience Platform提供执行用户档案服务引入所需的时间。

* 设置不会立即利用用户档案的旅程。 例如，如果旅程旨在确认帐户创建，则体验事件可能包含发送第一条确认消息（名、姓、电子邮件地址等）所需的信息。