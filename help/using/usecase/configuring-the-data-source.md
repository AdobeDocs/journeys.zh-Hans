---
product: adobe campaign
title: 配置数据源
description: 了解如何为历程简单用例配置数据源
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 5%

---

# 配置数据源{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


在我们的用例中，我们希望为消息使用个性化数据。 我们还需要检查这个人是不是女人。 此信息存储在Real-time Customer Profile数据库中。 **技术用户**&#x200B;需要检查这些字段是否在内置的Adobe Experience Platform数据源中定义。

有关数据源配置的其他信息，请参阅[此页面](../datasource/about-data-sources.md)。

1. 在菜单窗格中，选择&#x200B;**[!UICONTROL Admin]**。 在&#x200B;**[!UICONTROL Data sources]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Manage]**。
1. 选择内置的Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在字段组中，检查是否选择了以下字段：

   * _人员>姓名>名字_
   * _人员>姓名>姓氏_
   * _人员>性别_
   * _个人电子邮件>地址_

1. 单击 **[!UICONTROL Save]**。

数据源现已配置完毕，可随时用于您的旅程。
