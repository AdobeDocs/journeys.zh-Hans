---
product: adobe campaign
title: 配置事件
description: 了解如何为历程高级用例配置事件
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 9%

---

# 配置事件 {#concept_sbp_5cy_w2b}

在我们的情景中，每当一个人进入马尔顿酒店和餐厅时，我们都需要收到一个活动。 的 **技术用户** 需要配置我们希望系统在我们的历程中侦听的两个事件。

有关事件配置的其他信息，请参阅 [本页](../event/about-events.md).

1. 在顶部菜单中，单击 **[!UICONTROL Events]** 选项卡，单击 **[!UICONTROL Add]** 创建新事件。

   ![](../assets/journeyuc1_1.png)

1. 我们输入的名称中不带空格或特殊字符：&quot;LobbyBeacon&quot;。

   ![](../assets/journeyuc2_1.png)

1. 然后，我们选择架构并定义此事件所需的有效负载。 我们从XDM标准化模型中选择所需的字段。 我们需要Experience CloudID来识别实时客户资料数据库中的人员：&quot;endUserIDs > _experience > mcid > id&quot;。

   我们还需要注册令牌才能发送推送消息：&quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   将自动为此事件生成ID。 此ID存储在 **[!UICONTROL eventID]** 字段(“_experience > campaign > orchestration > eventID”)。 推送事件的系统不应生成ID，它应使用有效负荷预览中提供的ID。 在我们的用例中，此ID用于标识信标位置。 每当人员在大堂信标附近行走时，都会发送一个包含此特定事件ID的事件。 同样的原则也适用于餐馆信标事件。 这允许系统知道哪些信标触发了事件发送。

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >字段列表因架构而异。 根据架构定义，某些字段可能是必填的，并且是预选的。

1. 我们需要选择命名空间。根据模式属性预先选择命名空间。您可以使命名空间保持处于预选状态。有关命名空间的更多信息，请参阅[此页面](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc2_4.png)

1. 根据模式属性和选择的命名空间预先选择键。 你可以留着它。

   ![](../assets/journeyuc2_4bis.png)

1. 单击 **[!UICONTROL Save]**。

1. 单击 **[!UICONTROL View Payload]** 图标来预览系统预期的有效负载，并将其共享给负责事件发送的人员。  需要在Mobile服务管理控制台的回发中配置此负载。

   ![](../assets/journeyuc2_5.png)

同样，创建“RestaurantBeacon”事件。 您的两个信标事件已创建，现在可用于我们的历程。 现在，您需要配置移动应用程序，以便它可以将预期的有效负载发送到流摄取API端点。 请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
