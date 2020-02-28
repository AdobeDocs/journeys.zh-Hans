---
title: 定义事件键
description: 了解如何定义活动密钥
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


# 定义事件键 {#concept_ond_hqt_52b}

关键是字段或字段组合是事件有效负荷数据的一部分，这将允许系统识别与事件关联的人员。 密钥可以是Experience Cloud ID、CRM ID或电子邮件地址。

如果您计划利用存储在实时客户配置文件数据库中的数据，则必须选择在实时客户配置文件服务中定义为配置文件标识的信息作为事件密钥 [](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)。

它将允许系统执行事件与个人个人资料之间的协调。 如果选择的架构具有主标识，则预填 **[!UICONTROL Key]** 充 **[!UICONTROL Namespace]** 和字段。 如果未定义标识，则我们选择 _identityMap > id_ 作为主键。 然后，您必须选择一个命名空间，然后使用identityMap > id预填充( **[!UICONTROL Namespace]** 在字段下 _方)键_。

选择字段时，主标识字段将被标记。

![](../assets/primary-identity.png)

如果您需要使用其他密钥（如CRM ID或电子邮件地址），您需要手动添加它：

1. 在字段内 **[!UICONTROL Key]** 或铅笔图标上单击。

   ![](../assets/journey16.png)

1. 在有效负荷字段列表中选择作为键的字段。 您还可以切换到高级表达式编辑器以创建更复杂的键（例如，事件的两个字段的串联）。 请参阅下面的部分。

   ![](../assets/journey20.png)

当收到事件时，键的值将允许系统识别与事件关联的人。 与命名空间(请参 [](../event/selecting-the-namespace.md)阅)关联后，该键可用于在Adobe Experience Platform上执行查询。 请参见 [](../building-journeys/about-orchestration-activities.md)。钥匙还用于检查某人是否在旅程中。 事实上，一个人不可能在同一旅程中处于两个不同的位置。 因此，系统不允许同一密钥（例如，密钥CRMID=3224）在同一旅程的不同位置。

如果要执行其他操作，您还可以访&#x200B;**[!UICONTROL Advanced mode]**&#x200B;问高级表达式函数()。 这些函数允许您处理用于执行特定查询的值，例如更改格式、执行字段连接，只考虑字段的一部分（例如10个前字符）。 请参见 [](../expression/expressionadvanced.md)。
