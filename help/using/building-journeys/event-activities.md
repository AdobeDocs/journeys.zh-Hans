---
title: 关于事件活动
description: 了解事件活动
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# 关于事件活动 {#concept_rws_1rt_52b}

由技术用户配置的事件( [](../event/about-events.md)请参阅)均显示在调色板的左侧的第一个类别中。

![](../assets/journey43.png)

始终通过拖放开始活动来事件您的旅程。 您还可以多次单击它。

![](../assets/journey44.png)

单击画布中的事件活动时，将显示活动配置窗格。 默认情况下，当您多次使用相同的事件时，将向画布中的事件名称添加一个递增的编号。 此外，您还可以使用该字 **[!UICONTROL Label]** 段向事件名称添加后缀，该名称将显示在画布中您的活动下。 这在画布中识别事件非常有用，尤其是当您多次使用相同事件时。 它还使得在出现错误时调试更简单，并使报告更易于阅读。

![](../assets/journey33.png)

## 高级使用： 事件并行等待{#section_vxv_h25_pgb}

**你怎么能只在某段时间听事件?**

位于旅程中的事件活动无限地监听事件。 要仅在特定时间内监听事件，必须添加与事件路径平行的等待活动。 然后，该旅程将在等待活动中指定的时间内侦听事件。 如果在此期间收到事件，则人员将进入事件路径。 否则，客户将进入等待路径。

例如，您向客户发送了欢迎优先推送，并且您希望仅在客户在接下来的6小时内进入餐厅时发送餐点折扣推送。 为此，您将创建第二条路径(与餐厅事件一平行)，并设置6小时的等待活动。 如果在欢迎推送后不到6小时收到餐厅事件，则发送餐点折扣推送活动。 如果在接下来的6小时内没有收到餐馆事件，则该人将通过等待路径。

![](../assets/journeyuc2_31.png)
