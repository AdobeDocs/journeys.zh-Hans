---
title: 自定义操作限制
description: 了解自定义操作限制
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 295112e2d18fd275a0fd2826aa8bd87a8ed12636
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 4%

---


# 自定义操作限制 {#concept_lh2_df1_2gb}

以下是有关使用自定义操作的一些限制：

* 没有发送卷缓冲／平滑。
* 在出现错误时系统地执行两个重试。 无法根据收到的错误消息调整重试数。
* 内置事件 **[!UICONTROL Reaction]** 允许您对现成操作做出响应(请参阅 [](../building-journeys/event-activities.md))。 如果要对通过自定义操作发送的消息做出响应，则需要配置专用事件。
* 自定义操作URL不支持动态参数。
* 仅支持POST和PUT调用方法。
* 查询参数或标题的名称不能与“”开始。 或“$”。
* 不允许使用IP地址。
* 内部Adobe地址(.adobe.) 不允许。
