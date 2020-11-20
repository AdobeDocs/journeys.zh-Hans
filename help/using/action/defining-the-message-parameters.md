---
product: adobe campaign
solution: Journey Orchestration
title: 定义消息参数
description: 了解如何定义消息参数
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# 定义消息参数 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在部 **[!UICONTROL Message parameters]** 分中，粘贴JSON有效负荷的示例以发送到外部服务。

![](../assets/customactionpayloadmessage.png)

您将能够定义参数类型(例如：字符串、整数等)。

您还可以选择指定参数是常数还是变量：

* 常数表示参数的值由技术人员在操作配置窗格中定义。 在整个旅程中，价值始终相同。 在旅程中使用自定义操作时，不会有所不同，营销人员也不会看到这一点。 例如，它可能是第三方系统所需的ID。 在这种情况下，切换常数／变量右侧的字段是传递的值。
* 变量表示参数的值将发生变化。 在旅程中使用此自定义操作的营销人员可以自由地传递所需值或指定检索此参数值的位置(例如，从事件、从Adobe Experience Platform等)。 在这种情况下，切换常数／变量右侧的字段是营销人员在命名此参数的旅程中将看到的标签。

![](../assets/customactionpayloadmessage2.png)
