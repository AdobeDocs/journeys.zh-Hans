---
product: adobe campaign
title: 选择命名空间
description: 了解如何选择命名空间
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 4%

---

# 选择命名空间 {#concept_ckb_3qt_52b}

命名空间允许您定义用于标识与事件关联的人员的键类型。 其配置是可选的。 如果要在您的历程中检索来自[实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)的其他信息，则需要此信息。 如果您仅使用来自第三方系统的数据通过自定义数据源，则不需要命名空间定义。

您可以使用其中一个预定义命名空间，或使用身份命名空间服务创建新的一个预定义命名空间。 请参见此[页面](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html)。

如果选择具有主标识的架构，则会预填充&#x200B;**[!UICONTROL Key]**&#x200B;和&#x200B;**[!UICONTROL Namespace]**&#x200B;字段。 如果未定义标识，我们将选择&#x200B;_identityMap > id_&#x200B;作为主键。 然后，您必须选择命名空间，并使用&#x200B;_identityMap > id_&#x200B;预填充键（在&#x200B;**[!UICONTROL Namespace]**&#x200B;字段下）。

选择字段时，主标识字段会进行标记。

![](../assets/primary-identity.png)


从下拉列表中选择一个命名空间。

![](../assets/journey17.png)

每个历程只允许一个命名空间。 如果您在同一历程中使用多个事件，则它们需要使用相同的命名空间。 请参阅[此页](../building-journeys/journey.md)。
