---
product: adobe campaign
title: 定义消息参数
description: 了解如何定义消息参数
feature: 历程
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: eb765d2f12ade397e124281f52213bb3e58263cb
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# 定义消息参数 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在&#x200B;**[!UICONTROL Message parameters]**&#x200B;部分中，粘贴要发送到外部服务的JSON有效负载示例。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>有效负载中的字段名称不能包含“。” 字符. 不能以“$”字符开头。

您将能够定义参数类型(例如：字符串、整数等)。

您还可以选择指定参数是常量还是变量：

* 常量表示参数的值由技术人员在操作配置窗格中定义。 跨历程的值将始终相同。 在历程中使用自定义操作时，它不会有所不同，营销人员也不会看到它。 例如，它可能是第三方系统所需的ID。 在这种情况下，切换常量/变量右侧的字段是传递的值。
* 变量表示参数的值会有所不同。 在历程中使用此自定义操作的营销人员可以自由地传递所需的值，或指定在何处检索此参数的值(例如，从事件、从Adobe Experience Platform等)。 在这种情况下，切换常量/变量右侧的字段是营销人员在命名此参数的历程中将看到的标签。

![](../assets/customactionpayloadmessage2.png)
