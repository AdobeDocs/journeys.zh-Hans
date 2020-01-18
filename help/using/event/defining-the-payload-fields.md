---
title: 定义有效负荷字段
description: 了解如何定义有效负荷字段
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 定义有效负荷字段 {#concept_yrw_3qt_52b}

有效负荷定义允许您选择系统希望从旅程中的事件接收的信息以及确定与事件关联的人员的键。 有效负荷基于Experience Cloud XDM字段定义。 有关XDM的详细信息，请参阅本 [页](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html)。

1. 从列表中选择一个XDM架构，然后单击字 **[!UICONTROL Payload]**段或图标**[!UICONTROL Edit]** 上。

   ![](../assets/journey8.png)

   此时将显示架构中定义的所有字段。 字段列表因架构而异。 您可以搜索特定字段，或使用筛选器显示所有节点和字段，或仅显示选定的字段。 根据架构定义，某些字段可能是必填的并且是预先选择的。 您无法取消选择它们。

   >[!NOTE]
   >
   >确保已将“编排”混音添加到XDM架构中。 这将确保您的架构包含使用旅程安排所需的所有信息。

   ![](../assets/journey9.png)

1. 选择要从活动接收的字段。 这些字段是业务用户在旅程中将利用的字段。 它们还必须包含用于标识与活动关联的人员的密钥(请参 [](../event/defining-the-event-key.md)阅)。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >该字 **[!UICONTROL eventID]**段会自动添加到所选字段列表中，以便旅程安排可以识别该事件。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 请参见[](../event/previewing-the-payload.md)。

1. 选择完所需的字段后，单击或 **[!UICONTROL Save]**按下**[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   选定字段的数量将显示在字段 **[!UICONTROL Payload]**中。

   ![](../assets/journey12.png)
