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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 自定义操作限制 {#concept_lh2_df1_2gb}

以下是有关使用自定义操作的一些限制：

* 没有卷限制或发送卷缓冲／平滑。
* 系统地在出错时执行两次重试。 您无法根据收到的错误消息调整重试次数。
* 内置事 **[!UICONTROL Reaction]**件允许您对开箱即用的操作做出反应(请参阅[](../building-journeys/event-activities.md)。 如果要对通过自定义操作发送的消息做出响应，则需要配置专用活动。
* 自定义操作URL不支持动态参数。
* 仅支持POST和PUT调用方法。
* 查询参数或标题的名称不能以“.”开头 或“$”。
* 不允许使用IP地址。
* 内部Adobe地址(.adobe.)不允许。
