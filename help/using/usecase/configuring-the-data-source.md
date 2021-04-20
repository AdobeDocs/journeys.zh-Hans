---
product: adobe campaign
solution: Journey Orchestration
title: 配置数据源
description: 了解如何为旅程中的简单用例配置数据源
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%

---


# 配置数据源{#concept_ax3_bcy_w2b}

在我们的用例中，我们希望将个性化数据用于我们的消息。 我们还需要检查一下，这个人是女人。 此信息存储在实时客户用户档案数据库中。 **技术用户**&#x200B;需要检查这些字段是否在内置的Adobe Experience Platform数据源中定义。

有关数据源配置的其他信息，请参阅[此页](../datasource/about-data-sources.md)。

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Data Sources]**&#x200B;选项卡，然后选择内置Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在字段组中，检查是否选择了以下字段：

   * _person > name > firstName_
   * _person > name > lastName_
   * _“_
   * _personalEmail >地址_

1. 单击 **[!UICONTROL Save]**.

数据源现已配置好，可在您的旅程中使用。
