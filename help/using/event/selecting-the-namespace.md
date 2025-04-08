---
product: adobe campaign
title: 选择命名空间
description: 了解如何选择命名空间
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# 选择命名空间 {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


命名空间允许您定义用于识别与事件关联的人员的键类型。 其配置是可选的。 如果您想在历程中检索来自[实时客户个人资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)的其他信息，则需要此项。 如果您仅使用来自第三方系统的数据（通过自定义数据源），则不需要命名空间定义。

您可以使用其中一个预定义命名空间，也可以使用Identity Namespace Service创建新命名空间。 请参阅此[页面](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans)。

如果选择具有主标识的架构，则会预填充&#x200B;**[!UICONTROL Key]**&#x200B;和&#x200B;**[!UICONTROL Namespace]**&#x200B;字段。 如果未定义标识，我们选择&#x200B;_identityMap > id_&#x200B;作为主键。 然后，您必须选择一个命名空间，并使用&#x200B;_identityMap > id_&#x200B;预填充键（在&#x200B;**[!UICONTROL Namespace]**&#x200B;字段下）。

选择字段时，将标记主要标识字段。

![](../assets/primary-identity.png)


从下拉列表中选择一个命名空间。

![](../assets/journey17.png)

每个历程只允许一个命名空间。 如果您在同一历程中使用多个事件，则需要使用相同的命名空间。 请参阅[此页](../building-journeys/journey.md)。
