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

键值是字段或字段组合是事件有效负载数据的一部分，这将允许系统识别与事件关联的人员。 例如，密钥可以是Experience CloudID、CRM ID或电子邮件地址。

如果您计划利用存储在Real-time Customer Profile数据库中的数据，则必须选择您在中定义为用户档案标识的信息（作为事件键） [Real-time Customer Profile Service](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans).

它将允许系统在事件和个人配置文件之间执行协调。 如果选择具有主标识的架构，则 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 字段是预填充的。 如果未定义标识，则选择 _identityMap > id_ 作为主键。 然后，您必须选择一个命名空间，并且密钥将会预填充(在 **[!UICONTROL Namespace]** 字段)，使用 _identityMap > id_.

选择字段时，将标记主要标识字段。

![](../assets/primary-identity.png)

如果您需要使用其他密钥，例如CRM ID或电子邮件地址，则需要手动添加：

1. 在 **[!UICONTROL Key]** 字段或铅笔图标上。

   ![](../assets/journey16.png)

1. 在有效负载字段列表中选择选为键的字段。 您还可以切换到高级表达式编辑器以创建更复杂的键（例如，事件的两个字段的连接）。 请参阅本节中的以下内容。

   ![](../assets/journey20.png)

在收到事件时，键的值将允许系统识别与事件关联的人员。 与命名空间关联(请参阅 [此页面](../event/selecting-the-namespace.md))，密钥可用于对Adobe Experience Platform执行查询。 请参阅[此页](../building-journeys/about-orchestration-activities.md)。密钥还用于检查人员是否正在旅程中。 事实上，一个人不可能在同一旅程中的两个不同位置。 因此，系统不允许同一密钥（例如密钥CRMID=3224）位于同一历程中的不同位置。

您还可以访问高级表达式函数(**[!UICONTROL Advanced mode]**)。 这些函数允许您处理用于执行特定查询的值，例如更改格式、执行字段连接，仅考虑字段的一部分（例如10个前字符）。 请参阅[此页](../expression/expressionadvanced.md)。
