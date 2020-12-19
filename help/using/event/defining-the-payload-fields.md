---
product: adobe campaign
solution: Journey Orchestration
title: 定义有效负载字段
description: 了解如何定义有效负荷字段
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---


# 定义有效负载字段 {#concept_yrw_3qt_52b}

有效负荷定义允许您选择系统希望从旅程中的事件接收的信息，以及确定与事件关联的人员的键。 有效负荷基于Experience CloudXDM字段定义。 有关XDM的详细信息，请参阅[此页](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html)。

1. 从列表中选择一个XDM模式，然后单击&#x200B;**[!UICONTROL Payload]**&#x200B;字段或&#x200B;**[!UICONTROL Edit]**&#x200B;图标。

   ![](../assets/journey8.png)

   将显示模式中定义的所有字段。 字段的列表因模式而异。 您可以搜索特定字段或使用过滤器显示所有节点和字段或仅显示选定字段。 根据模式定义，某些字段可能是必填字段并且是预选字段。 无法取消选择它们。

   >[!NOTE]
   >
   >确保已将“编排”混音添加到XDM模式。 这将确保您的模式包含使用[!DNL Journey Orchestration]所需的所有信息。

   ![](../assets/journey9.png)

1. 选择您希望从事件接收的字段。 这些是业务用户在旅程中将利用的字段。 它们还必须包含用于标识与事件关联的人员的密钥（请参阅[此页](../event/defining-the-event-key.md)）。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >对于系统生成的事件,**[!UICONTROL eventID]**&#x200B;字段会自动添加到所选字段的列表中，以便[!DNL Journey Orchestration]可以识别事件。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

1. 选择完所需字段后，单击&#x200B;**[!UICONTROL Save]**&#x200B;或按&#x200B;**[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   选定字段的数量显示在&#x200B;**[!UICONTROL Payload]**&#x200B;字段中。

   ![](../assets/journey12.png)
