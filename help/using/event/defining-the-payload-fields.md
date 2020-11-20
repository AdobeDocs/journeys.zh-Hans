---
product: adobe campaign
solution: Journey Orchestration
title: 定义有效负载字段
description: 了解如何定义有效负荷字段
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 6%

---


# 定义有效负载字段 {#concept_yrw_3qt_52b}

有效负荷定义允许您选择系统希望从旅程中的事件接收的信息，以及确定与事件关联的人员的键。 有效负荷基于Experience CloudXDM字段定义。 For more information on XDM, refer to [this page](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html).

1. 从列表中选择一个XDM模式，然后单 **[!UICONTROL Payload]** 击字段或图 **[!UICONTROL Edit]** 标。

   ![](../assets/journey8.png)

   将显示模式中定义的所有字段。 字段的列表因模式而异。 您可以搜索特定字段或使用过滤器显示所有节点和字段或仅显示选定字段。 根据模式定义，某些字段可能是必填字段并且是预选字段。 无法取消选择它们。

   >[!NOTE]
   >
   >确保已将“编排”混音添加到XDM模式。 这将确保您的模式包含所有需要处理的信息 [!DNL Journey Orchestration]。

   ![](../assets/journey9.png)

1. 选择您希望从事件接收的字段。 这些是业务用户在旅程中将利用的字段。 它们还必须包含用于标识与事件关联的人员的键(请参 [阅此页](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >字 **[!UICONTROL eventID]** 段会自动添加到所选字段的列表中，以 [!DNL Journey Orchestration] 便识别事件。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

1. 选择完所需字段后，单击或 **[!UICONTROL Save]** 按下 **[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   选定字段的数量将显示在字 **[!UICONTROL Payload]** 段中。

   ![](../assets/journey12.png)
