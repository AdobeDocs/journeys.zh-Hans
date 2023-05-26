---
product: adobe campaign
title: 关于Adobe Analytics数据
description: 了解如何利用Adobe Analytics数据
feature: Journeys
role: User
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 9%

---

# 利用Adobe Analytics数据{#analytics-data}

>[!NOTE]
>
>本节仅适用于需要使用Adobe Analytics数据的基于规则的事件和客户。

您可以利用已在捕获并流入到Platform中的所有Adobe Analytics行为事件数据，以触发历程并自动化客户体验。

要使此功能正常工作，您需要在Adobe Experience Platform中激活要利用的报表包：

1. 在Adobe Experience Platform中，选择 **[!UICONTROL Sources]** 则 **[!UICONTROL Add data]** 在Adobe Analytics部分中。 此时将显示可用Adobe Analytics报表包的列表。

1. 选择要启用的报表包，然后单击 **[!UICONTROL Next]** 并单击 **[!UICONTROL Finish]**.

1. 与Alpha程序联系人共享源数据ID。

这将为该报表包启用Analytics Source Connector。 无论何时收到数据，这些数据都会转换为Experience事件并发送到Adobe Experience Platform中。

![](../assets/alpha-event9.png)

有关Adobe Analytics源连接器的更多信息，请参阅 [文档](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 和 [教程](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans).
