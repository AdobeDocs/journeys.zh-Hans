---
title: 配置数据源
description: 了解如何为旅程中的简单用例配置数据源
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 配置数据源{#concept_ax3_bcy_w2b}

在我们的使用案例中，我们希望将个性化数据用于我们的消息。 我们还需要检查一下这个人是女人。 此信息存储在实时客户档案数据库中。 技 **术用户需要检查** ，这些字段是否在内置的Experience Platform数据源中定义。

有关数据源配置的其他信息，请参阅 [](../datasource/about-data-sources.md)。

1. 在顶部菜单中，单击选 **[!UICONTROL Data Sources]**项卡，然后选择内置Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在字段组中，检查是否已选择以下字段：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人物>性别_
   * _personalEmail >地址_

1. 单击 **[!UICONTROL Save]**.

数据源现已配置好，可在您的旅程中使用。
