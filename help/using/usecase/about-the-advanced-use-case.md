---
title: 关于高级用例
description: 深入了解高级用例旅程
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# 关于高级用例{#concept_vzy_ncy_w2b}

## 用途 {#purpose}

我们以一个叫马尔顿的酒店品牌为例， 在他们的酒店里，他们把信标设备放在了所有战略区域附近：大堂、楼板、餐厅、健身房、游泳池等。

>[!NOTE]
>
>在此用例中，我们使用Adobe Campaign standard发送消息。

在此使用案例中，我们将了解当客户在特定信标附近行走时如何实时向客户发送个性化消息。

首先，我们要在一个人进入马尔顿酒店时，马上发送消息。 我们希望仅在此人在过去24小时内未收到我们的任何通信时发送消息。

然后，我们检查两个条件：

* 如果此人不是忠诚会员，我们会向他发送电子邮件以加入忠诚会员资格优惠。
* 如果此人已经是忠诚会员，我们会检查他是否有房间预订：
   * 如果他没有，我们会给他发送一份房费推送通知。
   * 如果他有，我们会向他发送欢迎推送通知。 如果他在6小时内进入餐厅，我们会给他发送推送通知，并在一餐时给予折扣。

![](../assets/journeyuc2_29.png)

对于此用例，我们需要创建两个事件(请参阅 [](../usecase/configuring-the-events.md)):

* 当客户进入酒店时将推送到系统的大堂信标事件。
* 当客户进入餐馆时将推送的餐馆信标事件。

我们需要配置到两个数据源的连接(请参 [](../usecase/configuring-the-data-sources.md)阅):

* 内置的Experience platform数据源，用于检索我们两个条件（忠诚度会员资格和上次联系日期）的信息以及消息个性化信息。
* 该酒店预订系统检索该预订状态信息。

## 先决条件 {#prerequisites}

对于我们的用例，我们设计了三个Adobe Campaign Standard交易消息模板。 我们使用活动事务消息模板。 Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign standard配置为发送电子邮件和推送通知。

Experience Cloud ID用作在酒店预订系统中识别客户的密钥。

当客户在信标附近检测到事件时，从其移动电话发送事件。 您需要设计移动应用程序，将事件从客户的手机发送到移动SDK。

忠诚度会员字段是自定义字段，已添加到XDM中以用于我们的特定组织ID。
