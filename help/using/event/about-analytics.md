---
product: adobe campaign
title: 关于Adobe Analytics数据
description: 了解如何利用Adobe Analytics数据
feature: Journeys
role: User
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# 利用Adobe Analytics数据{#analytics-data}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


>[!NOTE]
>
>本节仅适用于需要使用Adobe Analytics数据的基于规则的事件和客户。

您可以利用已在捕获并流入到Platform中的所有Adobe Analytics行为事件数据，以触发历程并自动化客户体验。

要使此功能正常工作，您需要在Adobe Experience Platform中激活要利用的报表包：

1. 在Adobe Experience Platform中，在Adobe Analytics部分中选择&#x200B;**[!UICONTROL Sources]**，然后选择&#x200B;**[!UICONTROL Add data]**。 此时会显示可用Adobe Analytics报表包的列表。

1. 选择要启用的报表包，单击&#x200B;**[!UICONTROL Next]**，然后单击&#x200B;**[!UICONTROL Finish]**。

1. 与您的Alpha程序联系人共享源数据ID。

这将启用该报表包的Analytics Source Connector。 无论何时收到数据，这些数据都会转换为Experience事件并发送到Adobe Experience Platform中。

![](../assets/alpha-event9.png)

有关Adobe Analytics源连接器的更多信息，请参阅[文档](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)和[教程](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。
