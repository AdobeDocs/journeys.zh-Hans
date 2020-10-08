---
title: 配置事件
description: 了解如何为旅程高级用例配置事件
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---


# 配置事件 {#concept_sbp_5cy_w2b}

在我们的情形中，每次有人进入马尔顿酒店和餐厅时，我们都需要收到事件。 技 **术用户** 需要配置我们希望系统在旅程中监听的两个事件。

有关事件配置的其他信息，请参阅 [](../event/about-events.md)。

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. 我们输入名称时不带空格或特殊字符：“LobbyBeacon”。

   ![](../assets/journeyuc2_1.png)

1. 然后，我们选择模式并定义此事件预期的有效负荷。 从XDM标准化模型中选取所需的字段。 我们需要Experience CloudID来识别实时客户用户档案数据库中的人：“endUserIDs > _experience > mcid > id”。

   我们还需要注册令牌来发送推送消息：&quot;_experience >活动>消息>用户档案> pushNotificationTokens >令牌&quot;

   此事件会自动生成ID。 此ID存储在字 **[!UICONTROL eventID]** 段中(“_experience >活动>业务流程>事件ID”)。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 在我们的用例中，此ID用于标识信标位置。 每次有人在大堂信标附近散步时，都会发送包含此特定事件ID的事件。 同样的原则也适用于餐馆信标事件。 这使系统能够知道哪个信标触发了事件发送。

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >字段的列表因模式而异。 根据模式定义，某些字段可能是必填字段并且是预选字段。

1. 我们需要选择命名空间。根据模式属性预先选择命名空间。您可以使命名空间保持处于预选状态。有关命名空间的详细信息，请参阅[](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc2_4.png)

1. 根据模式属性和选定的命名空间预选键。 你可以留着它。

   ![](../assets/journeyuc2_4bis.png)

1. 单击 **[!UICONTROL Save]**.

1. 单击该 **[!UICONTROL View Payload]** 图标以预览系统预期的有效负荷，并将其共享给负责事件发送的人员。  此负载需要在Mobile Services管理控制台的回传中配置。

   ![](../assets/journeyuc2_5.png)

同样，创建“RestaurantBeacon”事件。 您的两个信标事件已创建，现在可用于我们的旅程。 现在，您需要配置移动应用程序，以便它能够将期望的有效负荷发送到流摄取API端点。 请参见 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
