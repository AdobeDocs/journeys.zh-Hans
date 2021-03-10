---
product: adobe campaign
solution: Journey Orchestration
title: 定义有效负载字段
description: 了解如何定义有效负荷字段
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 6%

---


# 定义有效负载字段 {#concept_yrw_3qt_52b}

有效负荷定义允许您选择系统希望从旅程中的事件接收的信息，以及确定与事件关联的人员的键。 负载基于Experience CloudXDM字段定义。 有关XDM的详细信息，请参阅[此页](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html)。

1. 从列表中选择一个XDM模式，然后单击&#x200B;**[!UICONTROL Payload]**&#x200B;字段或&#x200B;**[!UICONTROL Edit]**&#x200B;图标。

   ![](../assets/journey8.png)

   将显示模式中定义的所有字段。 字段的列表因模式而异。 您可以搜索特定字段或使用过滤器显示所有节点和字段，或仅显示所选字段。 根据模式定义，某些字段可能是必填的并且是预选的。 您无法取消选择它们。 默认情况下，事件必须正确接收Journey Orchestration的所有字段都处于选中状态。

   >[!NOTE]
   >
   >确保已将“业务流程”混音添加到XDM模式。 这将确保您的模式包含使用[!DNL Journey Orchestration]所需的所有信息。

   ![](../assets/journey9.png)

1. 选择要从事件接收的字段。 这些是业务用户在旅程中将利用的字段。 它们还必须包含用于标识与事件关联的人员的密钥（请参阅[此页](../event/defining-the-event-key.md)）。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >对于系统生成的事件,**[!UICONTROL eventID]**&#x200B;字段会自动添加到所选字段的列表中，以便[!DNL Journey Orchestration]可以标识事件。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

1. 选择完所需字段后，单击&#x200B;**[!UICONTROL Save]**&#x200B;或按&#x200B;**[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   选定字段的数目将显示在&#x200B;**[!UICONTROL Payload]**&#x200B;字段中。

   ![](../assets/journey12.png)
