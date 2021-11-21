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

# Leveraging Adobe Analytics data{#analytics-data}

>[!NOTE]
>
>This section only applies for rule-based events and customers who need to use Adobe Analytics data.

您可以利用已在捕获并流入到平台中的所有Adobe Analytics行为事件数据，以触发历程并自动化客户体验。

For this to work, you need to activate, in Adobe Experience Platform, the report suite that you want to leverage:

1. 在Adobe Experience Platform中，选择 **[!UICONTROL Sources]** then **[!UICONTROL Add data]** 在Adobe Analytics部分。 此时会显示可用的Adobe Analytics报表包列表。

1. 选择要启用的报表包，单击 **[!UICONTROL Next]** 单击 **[!UICONTROL Finish]**.

1. 与Alpha程序联系人共享源数据ID。

This enables the Analytics source connector for that report suite. 每当数据传入时，它都会转换为体验事件并发送到Adobe Experience Platform。

![](../assets/alpha-event9.png)

For more information on the Adobe Analytics source connector, refer to the [documentation](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) and [tutorial](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans).
