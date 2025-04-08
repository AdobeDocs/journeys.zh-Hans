---
product: adobe campaign
title: 定义事件键
description: 了解如何定义事件键
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 2%

---

# 定义事件键 {#concept_ond_hqt_52b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


键值是字段或字段组合是事件有效负载数据的一部分，这将允许系统识别与事件关联的个人。 例如，密钥可以是Experience Cloud ID、CRM ID或电子邮件地址。

如果您计划利用存储在实时客户资料数据库中的数据，则必须选择在[实时客户资料服务](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)中定义为个人资料标识的信息，作为事件键。

它将允许系统在事件和个人配置文件之间执行协调。 如果选择具有主标识的架构，则会预填充&#x200B;**[!UICONTROL Key]**&#x200B;和&#x200B;**[!UICONTROL Namespace]**&#x200B;字段。 如果未定义标识，我们选择&#x200B;_identityMap > id_&#x200B;作为主键。 然后，您必须选择一个命名空间，并使用&#x200B;_identityMap > id_&#x200B;预填充键（在&#x200B;**[!UICONTROL Namespace]**&#x200B;字段下）。

选择字段时，将标记主要标识字段。

![](../assets/primary-identity.png)

如果您需要使用其他密钥，如CRM ID或电子邮件地址，则需要手动添加它：

1. 在&#x200B;**[!UICONTROL Key]**&#x200B;字段内或铅笔图标上单击。

   ![](../assets/journey16.png)

1. 在有效负载字段列表中选择已选作键的字段。 您还可以切换到高级表达式编辑器以创建更复杂的键（例如，两个事件字段的串联）。 请参阅本节中的下文。

   ![](../assets/journey20.png)

当收到事件时，键的值将允许系统识别与事件相关联的人员。 与命名空间关联（请参阅[此页面](../event/selecting-the-namespace.md)），密钥可用于在Adobe Experience Platform上执行查询。 查看[此页面](../building-journeys/about-orchestration-activities.md)。
密钥还用于检查人员是否正在旅程中。 事实上，一个人在同一历程中不能位于两个不同的位置。 因此，系统不允许相同的键（例如键CRMID=3224）位于同一历程的不同位置。

如果要执行其他操作，还可以访问高级表达式函数(**[!UICONTROL Advanced mode]**)。 利用这些函数，可处理用于执行特定查询的值，例如更改格式、执行字段连接，同时仅考虑字段的一部分（例如，前10个字符）。 请参阅[此页](../expression/expressionadvanced.md)。
