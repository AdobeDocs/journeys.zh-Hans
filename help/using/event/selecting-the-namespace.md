---
product: adobe campaign
solution: Journey Orchestration
title: 选择命名空间
description: 了解如何选择命名空间
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 12%

---


# 选择命名空间 {#concept_ckb_3qt_52b}

命名空间允许您定义用于标识与事件关联的人员的键类型。 其配置是可选的。 如果您想在旅程中检索来自实时客户用户档案的其 [他信息，则需要](https://docs.adobe.com/content/help/zh-Hans/experience-platform/profile/home.html)。 如果您仅使用来自第三方系统的数据通过自定义数据源，则不需要命名空间定义。

您可以使用其中一个预定义的命名空间，或使用身份识别服务创建新的标识。 Refer to this [page](https://docs.adobe.com/content/help/zh-Hans/experience-platform/identity/home.html).

如果您选择具有主标识的模式，则 **[!UICONTROL Key]** 会预 **[!UICONTROL Namespace]** 填和字段。 如果没有定义身份，则我们选 _择identityMap_ > id作为主键。 然后，您必须选择一个命名空间，然后使用identityMap > id预填( **[!UICONTROL Namespace]** 在字段 _下方)键_。

选择字段时，主标识字段将被标记。

![](../assets/primary-identity.png)


从下拉命名空间中选择列表。

![](../assets/journey17.png)

每个旅程只允许一个命名空间。 如果您在同一旅程中使用多个事件，则他们需要使用相同的命名空间。 请参阅[此页](../building-journeys/journey.md)。
