---
product: adobe campaign
title: 利用疲劳分数
description: 了解如何在历程中利用疲劳得分
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# 利用旅程 AI {#concept_dsh_1ry_wfb}

此用例将向您展示如何利用疲劳得分，以避免在您的历程中过度吸引客户。

>[!NOTE]
>
>预测疲劳得分功能仅适用于使用 [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## 配置事件 {#section_ptb_ws1_ffb}

按照 [本页](../event/about-events.md).

## 配置数据源 {#section_o3n_4yy_wfb}

执行以下步骤以选择内置数据源中的疲劳分数字段：

1. 在菜单窗格中，选择 **[!UICONTROL Admin]**. 在 **[!UICONTROL Data sources]** ，单击 **[!UICONTROL Manage]**.
1. 选择内置的Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 检查是否选择了用例所需的字段。
1. 单击 **[!UICONTROL Add a New Field Group]**，选择 **[!UICONTROL Profiles]** 模型并添加 **[!UICONTROL fatigueLevel]** 和 **[!UICONTROL fatigueScore]** 字段（下） _journeyAI > emailScore >疲劳_)。

   ![](../assets/journeyuc3_1.png)

1. 单击 **[!UICONTROL Save]**。

## 构建历程 {#section_uzm_pyy_wfb}

要创建、验证和发布历程，请按照 [本页](../building-journeys/journey.md).

在我们的用例中，我们将利用 **[!UICONTROL fatigueLevel]** 字段。 您还可以使用 **[!UICONTROL fatigueScore]** 字段。

执行以下步骤以利用历程中的疲劳级别：

1. 在历程中添加事件和条件。

   ![](../assets/journeyuc2_14.png)

1. 选择 **[!UICONTROL Data Source Condition]** 类型，然后在 **[!UICONTROL Expression]** 字段中单击。

   ![](../assets/journeyuc3_2.png)

1. 使用简单的表达式编辑器，查找 **[!UICONTROL fatigueLevel]** 字段(_ExperiencePlatformDataSource > JourneyAIScores >用户档案> journeyAI > emailScore >疲劳_)，将其拖到右侧并创建以下条件：&quot;fatigueLevel等于&quot;Low&quot;。 单击 **[!UICONTROL Ok]**。

   ![](../assets/journeyuc3_3.png)

   高级表达式为：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在条件中，为中等和高疲劳级别创建其他两个路径。

   ![](../assets/journeyuc3_4.png)

1. 现在，您可以为每个疲劳级别添加不同的操作。

   ![](../assets/journeyuc3_5.png)
