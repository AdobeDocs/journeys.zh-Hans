---
product: adobe campaign
title: 关于高级用例
description: 进一步了解历程高级用例
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: e7c3dde02837d31c5eb7d170cae7f142ce376175
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# 关于高级用例{#concept_vzy_ncy_w2b}

## 用途 {#purpose}

我们以一个叫马尔顿的酒店品牌为例。 在他们的酒店里，他们把信标设备定位在所有战略区域附近：大堂、地板、餐厅、健身房、游泳池等

>[!NOTE]
>
>在此用例中，我们使用Adobe Campaign Standard发送消息。

在此用例中，我们将了解如何在客户靠近特定信标时向客户实时发送个性化消息。

首先，我们想在某人进入马尔顿酒店后立即发送信息。 我们仅希望该人在过去24小时内未收到我们的任何通信时发送消息。

然后，我们检查两个条件：

* 如果此人不是忠诚会员，我们会向他发送电子邮件，以加入忠诚会员选件。
* 如果此人已是忠诚会员，我们会检查他是否有房间预订：
   * 如果他没有，我们会给他发一条带房费的推送通知。
   * 如果他有，我们会向他发送欢迎推送通知。 如果他在接下来的6小时内进入餐厅，我们会给他发一条推送通知，并在一餐时给予折扣。

![](../assets/journeyuc2_29.png)

对于此用例，我们需要创建两个事件（请参阅[此页面](../usecase/configuring-the-events.md)）：

* 客户进入酒店时将被推送到系统的大堂信标事件。
* 客户进入餐厅时将推送的餐馆信标事件。

我们需要配置与两个数据源的连接（请参阅[此页](../usecase/configuring-the-data-sources.md)）：

* 内置Adobe Experience Platform数据源，用于检索两个条件（会员资格和上次联系日期）的信息以及消息个性化信息。
* 酒店预订系统，用于检索预订状态信息。

## 先决条件 {#prerequisites}

对于我们的用例，我们设计了三个Adobe Campaign Standard事务型消息传递模板。 我们使用的是事件事务型消息模板。 请参见此[页面]()。

Adobe Campaign Standard配置为发送电子邮件和推送通知。

Experience CloudID用作在酒店预订系统中标识客户的键。

当客户在信标附近检测到事件时，会从其手机发送事件。 您需要设计一个移动应用程序，以将事件从客户的手机发送到Mobile SDK。

忠诚度会员字段是一个自定义字段，已添加到XDM中以用于我们的特定组织ID。
