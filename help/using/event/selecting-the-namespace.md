---
product: adobe campaign
title: 选择命名空间
description: 了解如何选择命名空间
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 选择命名空间 {#concept_ckb_3qt_52b}

命名空间允许您定义用于标识与事件关联的人员的键类型。 其配置是可选的。 如果要在您的历程中检索来自 [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans). 如果您仅使用来自第三方系统的数据通过自定义数据源，则不需要命名空间定义。

您可以使用其中一个预定义命名空间，或使用身份命名空间服务创建新的一个预定义命名空间。 请参阅 [页面](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans).

如果您选择的架构具有主标识，则 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 字段已预填充。 如果未定义身份，我们将选择 _identityMap > id_ 作为主键。 然后，您必须选择命名空间，并且该键值将被预填充(位于 **[!UICONTROL Namespace]** 字段)使用 _identityMap > id_.

选择字段时，主标识字段会进行标记。

![](../assets/primary-identity.png)


从下拉列表中选择一个命名空间。

![](../assets/journey17.png)

每个历程只允许一个命名空间。 如果您在同一历程中使用多个事件，则它们需要使用相同的命名空间。 请参阅[此页](../building-journeys/journey.md)。
