---
title: Journey Orchestration限制
description: 进一步了解Journey Orchestration限制
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 59b726388ee1c2c4b51ada9e7e5f7ca4eb6554b3
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# 限制{#limitations}

以下是与使用Journey Orchestration相关的限制。

## 一般操作限制

* 没有发送限制。 
* 在出现错误时系统地执行两个重试。 无法根据收到的错误消息调整重试数。 
* 内置的 **Reaction** 事件允许您对开箱即用的操作做出响应(请参阅 [此页](../building-journeys/reaction-events.md))。 如果要对通过自定义操作发送的消息做出响应，则需要配置专用事件。 
* 没有Adobe Campaign Classic按产品分类整合。
 
## 自定义操作限制

* 自定义操作URL不支持动态参数。 
* 仅支持POST和PUT调用方法。 
* 查询参数或标题的名称不能与“”开始。 或者 &quot;$&quot;. 
* 不允许使用IP地址。 
* 内部Adobe地址(.adobe.) 不允许。
 

## Adobe Campaign操作限制

* Adobe Campaign Standard交易消息传递在给定实例的渠道中每小时最大可发送50 000条消息。 请参阅 [Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
* 由于 **吞吐量限制** ，区段资格活动不应与Adobe Campaign Standard交易消息结合使用。
 
## 事件限制

* 用于启动客户旅程的流数据必须首先在Journey Orchestration中配置，才能获得唯一的业务流程ID。 此业务流程ID必须附加到进入Adobe Experience Platform的流负载。
 

## 数据源限制：

* 在客户旅程中可利用外部数据源实时查找外部数据。 这些源必须可以通过REST API使用，支持JSON并能够处理大量请求。