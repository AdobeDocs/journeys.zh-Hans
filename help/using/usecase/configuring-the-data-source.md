---
product: adobe campaign
title: 配置数据源
description: 了解如何为历程简单用例配置数据源
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 9%

---

# 配置数据源{#concept_ax3_bcy_w2b}

在我们的用例中，我们希望为消息使用个性化数据。 我们还需要检查这个人是不是女人。 此信息存储在Real-time Customer Profile数据库中。 此 **技术用户** 需要检查这些字段是否在内置的Adobe Experience Platform数据源中定义。

有关数据源配置的其他信息，请参阅 [此页面](../datasource/about-data-sources.md).

1. 在菜单窗格中，选择 **[!UICONTROL Admin]**. 在 **[!UICONTROL Data sources]** 部分中，单击 **[!UICONTROL Manage]**。
1. 选择内置的Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在字段组中，检查是否选择了以下字段：

   * _人员>姓名>名字_
   * _人员>姓名>姓氏_
   * _人员>性别_
   * _personalEmail >地址_

1. 单击 **[!UICONTROL Save]**。

数据源现已配置完毕，可随时用于您的旅程。
