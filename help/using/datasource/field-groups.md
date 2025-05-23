---
product: adobe campaign
title: 字段组
description: 了解字段组
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# 字段组 {#concept_ntl_ypt_52b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


字段组是可从数据源检索并在历程中使用的一组字段。

## 定义字段组 {#section_dsz_kjd_fjb}

对于每个数据源，您可以定义多个字段组。

例如，您可以创建一个字段组，其中包含电话号码、电子邮件、名字和个人资料的地址。 然后，您便能够在历程中使用此数据来创建条件。 例如，您可以决定仅在用户档案的电话号码不为空时发送短信。 如果为空，您可以发送电子邮件。

即使自动添加了默认名称，我们仍建议您为字段组提供一个名称。 事实上，字段组名称将对[!DNL Journey Orchestration]中的其他用户可见。 为字段组指定相关名称是一种最佳实践。

在历程中使用数据源字段时，系统将检索为该字段组定义的所有字段。 因此，最佳实践是仅选择历程所需的字段。 这将减少历程中的请求延迟，从而提高性能。 请注意，您可以稍后在字段组中轻松添加更多字段。

使用字段组的历程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。 您可以单击&#x200B;**[!UICONTROL View journeys]**&#x200B;按钮以显示使用此字段组的旅程列表。

>[!NOTE]
>
>请注意，如果字段组没有字段，则不会显示在表达式编辑器中。

![](../assets/journey3bis.png)

## 字段组生命周期 {#section_abk_njd_fjb}

您可以从未在任何草稿或实时历程中使用的字段组中添加或删除字段。

您可以添加，但无法从一个或多个草稿或实时历程中使用的字段组中删除字段。 这将避免中断历程。

要从一个或多个历程中使用的字段组中删除字段，请执行以下步骤。 让我们举一个名为“字段组A”的字段组为例。

1. 在字段组列表中，将光标置于“字段组A”上，然后单击右侧的&#x200B;**[!UICONTROL Duplicate]**&#x200B;图标。 例如，将复制的字段组命名为“字段组B”。
1. 在“字段组B”中，删除您不再需要的字段。
1. 在“字段组A”中，检查在何处使用此字段组。 此信息显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。
1. 打开所有使用“字段组A”的历程。
1. 创建每个历程的新版本。 使用“字段组A”编辑所有活动并选择“字段组B”。
1. 停止使用“字段组A”的旧版本历程。 然后，您应该没有使用“字段组A”的历程。
1. 删除“字段组A”，因为它已不再使用。
