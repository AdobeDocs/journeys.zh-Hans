---
product: adobe campaign
solution: Journey Orchestration
title: 配置事件
description: 了解如何为旅程简单用例配置事件
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 10%

---


# 配置事件{#concept_y44_hcy_w2b}

在我们的场景中，每当一个人走近位于温泉旁边的信标时，我们需要收到一个事件。 **技术用户**&#x200B;需要配置系统在我们的旅程中将侦听的事件。

有关事件配置的其他信息，请参阅[此页](../event/about-events.md)。

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Events]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新事件。

   ![](../assets/journeyuc1_1.png)

1. 我们输入名称时不加空格或特殊字符：“SpaBeacon”。

   ![](../assets/journeyuc1_2.png)

1. 然后，我们选择模式并定义此事件预期的有效负荷。 从XDM标准化模型中选取所需字段。 我们需要Experience CloudID来识别实时客户用户档案数据库中的人：_endUserIDs > experience > mcid > id_。 系统会为此事件自动生成ID。 此ID存储在&#x200B;**[!UICONTROL eventID]**&#x200B;字段(_体验>活动>业务流程> eventID_)中。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 在我们的用例中，此ID用于标识信标位置。 每当某人在Spa信标附近行走时，将发送包含此特定事件ID的事件。 这使系统能够知道哪个信标触发了事件发送。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >字段的列表因模式而异。 根据模式定义，某些字段可能是必填的并且是预选的。

1. 我们需要选择命名空间。根据模式属性预先选择命名空间。您可以使命名空间保持处于预选状态。有关命名空间的更多信息，请参阅[此页面](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc1_6.png)

1. 根据模式属性和选定的命名空间预选键。 你可以留着。

   ![](../assets/journeyuc1_5.png)

1. 单击 **[!UICONTROL Save]**.

1. 单击&#x200B;**[!UICONTROL View Payload]**&#x200B;图标以预览系统预期的有效负荷，并将其共享给负责事件发送的人员。 此负载需要在Mobile Services管理控制台的回发中配置。

   ![](../assets/journeyuc1_7.png)

   事件已准备好用于您的旅程。 您现在需要配置移动应用程序，以便它能够将预期的有效负荷发送到流摄取API端点。 请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。