---
product: adobe campaign
solution: Journey Orchestration
title: 关于高级用例
description: 深入了解旅程高级用例
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---


# 关于高级用例{#concept_vzy_ncy_w2b}

## 用途{#purpose}

我们以一个叫马尔顿的酒店品牌为例。 在他们的酒店里，他们把信标设备放在了所有战略区域附近：大堂、地板、餐厅、健身房、游泳池等。

>[!NOTE]
>
>在这种情况下，我们使用Adobe Campaign Standard发送消息。

在此用例中，我们将了解如何在客户靠近特定信标时实时向其发送个性化消息。

首先，我们想在一个人进入马尔顿酒店后立即发送消息。 仅当此人在过去24小时内未收到我们的任何通信时，我们才希望发送消息。

然后检查两个条件：

* 如果此人不是忠诚会员，我们会向他发送电子邮件，让他加入忠诚会员优惠。
* 如果此人已经是忠诚会员，我们会检查他是否有房间预订：
   * 如果他没有，我们会给他发送一条带房费的推送通知。
   * 如果他知道，我们会向他发送欢迎推送通知。 如果他在接下来的6小时内进入餐厅，我们会给他发送推送通知，并在一顿餐上打折。

![](../assets/journeyuc2_29.png)

对于此用例，我们需要创建两个事件（请参阅[此页](../usecase/configuring-the-events.md)）:

* 当客户进入酒店时将推送到系统的大堂信标事件。
* 当客户进入餐馆时，将推送的餐馆信标事件。

我们需要配置到两个数据源的连接（请参阅[此页](../usecase/configuring-the-data-sources.md)）:

* 内置的Adobe Experience Platform数据源，用于检索我们两个条件（忠诚会员资格和上次联系日期）的信息以及消息个性化信息。
* 酒店预订系统，用于检索预订状态信息。

## 先决条件{#prerequisites}

为了我们的用例，我们设计了三个Adobe Campaign Standard交易消息模板。 我们使用事件事务消息模板。 请参阅此[页面](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

Adobe Campaign Standard配置为发送电子邮件和推送通知。

Experience CloudID用作在酒店预订系统中识别客户的密钥。

当事件在信标附近被检测到时，从客户的移动电话发送数据。 您需要设计一个移动应用程序，将事件从客户的手机发送到移动SDK。

忠诚度成员字段是自定义字段，已添加到XDM中，用于我们的特定组织ID。
