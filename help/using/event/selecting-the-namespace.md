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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# 选择命名空间 {#concept_ckb_3qt_52b}

命名空间允许您定义用于标识与事件关联的人员的键类型。 其配置是可选的。 如果您想在旅程中检索来自实时客户用户档案的其他信 [息，则需要此信息](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)。 如果您仅使用来自第三方系统的数据通过自定义数据源，则不需要命名空间定义。

您可以使用其中一个预定义的标识，或使用标识命名空间服务创建新的标识。 Refer to this [page](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html).

如果选择具有主标识的模式，则 **[!UICONTROL Key]** 将预 **[!UICONTROL Namespace]** 填和字段。 如果未定义标识，则我们选 _择identityMap > id_ ，作为主键。 然后，您必须选择一个命名空间，然后使用identityMap > id预填充( **[!UICONTROL Namespace]** 在字段 _下方)键_。

选择字段时，主标识字段将被标记。

![](../assets/primary-identity.png)


从下拉命名空间中选择列表。

![](../assets/journey17.png)

每个旅程只允许一个命名空间。 如果您在同一旅程中使用多个事件，则他们需要使用相同的命名空间。 请参见 [](../building-journeys/journey.md)。
