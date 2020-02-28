---
title: 选择命名空间
description: 了解如何选择命名空间
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 411ecf0ec4dc6a87c4e129b40f2918799bef54bf

---


# 选择命名空间 {#concept_ckb_3qt_52b}

该命名空间允许您定义用于标识与活动关联的人员的密钥类型。 其配置是可选的。 如果要在旅程中检索来自实时客户档案的其 [他信息，则需要此信息](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)。 如果您仅使用来自第三方系统的数据通过自定义数据源，则不需要命名空间定义。

您可以使用其中一个预定义的名称，或使用Identity Namespace服务创建新名称。 Refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md).

如果选择的架构具有主标识，则预填 **[!UICONTROL Key]** 充 **[!UICONTROL Namespace]** 和字段。 如果未定义标识，则我们选 _择identityMap > id_ ，作为主键。 然后，您必须选择一个命名空间，然后使用identityMap > id预填充( **[!UICONTROL Namespace]** 在字段下 _方)键_。

选择字段时，主标识字段将被标记。

![](../assets/primary-identity.png)


从下拉列表中选择一个命名空间。

![](../assets/journey17.png)

每个旅程只允许一个命名空间。 如果您在同一旅程中使用多个事件，它们需要使用相同的命名空间。 请参见 [](../building-journeys/journey.md)。
