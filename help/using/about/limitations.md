---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration限制
description: 进一步了解Journey Orchestration限制
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 限制{#limitations}

以下是与使用Journey Orchestration相关的限制。

## 一般操作限制

* 没有发送限制。 
* 在出现错误时系统地执行两个重试。 无法根据收到的错误消息调整重试数。 
* 内置&#x200B;**Reaction**&#x200B;事件允许您对现成操作做出响应（请参阅此[页面](../building-journeys/reaction-events.md)）。 如果要对通过自定义操作发送的消息做出响应，则需要配置专用事件。 
* 没有Adobe Campaign Classic按产品分类整合。

## 旅程版本限制{#journey-versions-limitations}

* 从v1中的事件活动开始的旅程不能与其他版本中的事件开始。 您不能使用&#x200B;**区段资格**&#x200B;开始旅程。
* 从v1中的&#x200B;**区段资格**&#x200B;活动开始的旅程必须始终以其他版本的&#x200B;**区段资格**&#x200B;开始。
* 在新版本中，无法更改在&#x200B;**区段资格**（第一个节点）中选择的区段和命名空间。
* 在所有旅程版本中，重新进入规则必须相同。

## 区段资格{#segment-qualification}

* 由于吞吐量限制，**区段资格**&#x200B;活动不能与Adobe Campaign Standard事务消息结合使用。 请参阅[Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 自定义操作限制

* 自定义操作URL不支持动态参数。 
* 仅支持POST和PUT调用方法。 
* 查询参数或标题的名称不能与“”开始。 或者 &quot;$&quot;. 
* 不允许使用IP地址。 
* 内部Adobe地址(.adobe.) 不允许。
 

## Adobe Campaign操作限制

* Adobe Campaign Standard交易消息传递在给定实例的渠道中每小时最大可发送50 000条消息。 请参阅[Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 事件限制

* 用于启动客户旅程的流数据必须首先在Journey Orchestration中配置，才能获得唯一的业务流程ID。 此业务流程ID必须附加到进入Adobe Experience Platform的流负载。
 

## 数据源限制

* 在客户旅程中可利用外部数据源实时查找外部数据。 这些源必须可以通过REST API使用，支持JSON并能够处理大量请求。