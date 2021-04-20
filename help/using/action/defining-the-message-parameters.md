---
product: adobe campaign
solution: Journey Orchestration
title: 定义消息参数
description: 了解如何定义消息参数
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# 定义消息参数 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在&#x200B;**[!UICONTROL Message parameters]**&#x200B;部分，粘贴要发送到外部服务的JSON有效负荷示例。

![](../assets/customactionpayloadmessage.png)

您将能够定义参数类型(例如：字符串、整数等)。

您还可以选择指定参数是常量还是变量：

* 常量表示参数的值由技术人员在操作配置窗格中定义。 在整个旅程中，价值始终保持不变。 在客户旅程中使用自定义操作时，不会有任何不同，营销人员也不会看到。 例如，它可以是第三方系统所需的ID。 在这种情况下，切换常数/变量右侧的字段是传递的值。
* 变量表示参数的值将不同。 在旅程中使用此自定义操作的营销人员可以自由地传递所需的值或指定检索此参数值的位置(例如从事件、从Adobe Experience Platform等)。 在这种情况下，切换常量/变量右侧的字段是营销人员在命名此参数的旅程中将看到的标签。

![](../assets/customactionpayloadmessage2.png)
