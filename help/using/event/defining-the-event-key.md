---
product: adobe campaign
title: 定义事件键
description: 了解如何定义事件键
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 5%

---

# 定义事件键 {#concept_ond_hqt_52b}

键值是字段或字段组合是事件有效负载数据的一部分，它将允许系统识别与事件关联的人员。 键可以是Experience CloudID、CRM ID或电子邮件地址。

如果您计划利用存储在实时客户资料数据库中的数据，则必须选择在 [实时客户资料服务](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans).

它将允许系统执行事件与个人用户档案之间的协调。 如果您选择的架构具有主标识，则 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 字段已预填充。 如果未定义身份，我们将选择 _identityMap > id_ 作为主键。 然后，您必须选择命名空间，并且该键值将被预填充(位于 **[!UICONTROL Namespace]** 字段)使用 _identityMap > id_.

选择字段时，主标识字段会进行标记。

![](../assets/primary-identity.png)

如果您需要使用其他键（如CRM ID或电子邮件地址），则需要手动添加它：

1. 在 **[!UICONTROL Key]** 字段或铅笔图标上的。

   ![](../assets/journey16.png)

1. 在有效负载字段列表中选择作为键的字段。 您还可以切换到高级表达式编辑器以创建更复杂的键（例如，事件的两个字段的串联）。 请参阅下面的此部分。

   ![](../assets/journey20.png)

收到事件后，键值将允许系统识别与事件关联的人员。 与命名空间关联(请参阅 [本页](../event/selecting-the-namespace.md))，则可以使用键对Adobe Experience Platform执行查询。 请参阅[此页](../building-journeys/about-orchestration-activities.md)。键还用于检查人员是否处于历程中。 事实上，一个人不可能在同一旅程中处于两个不同的位置。 因此，系统不允许同一密钥（例如CRMID=3224）位于同一历程中的不同位置。

您还可以访问高级表达式函数(**[!UICONTROL Advanced mode]**)。 利用这些函数，可处理用于执行特定查询（如更改格式、执行字段连接）的值，只考虑字段的一部分（例如10个前字符）。 请参阅[此页](../expression/expressionadvanced.md)。
