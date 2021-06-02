---
product: adobe campaign
title: 利用疲劳分数
description: 了解如何在历程中利用疲劳得分
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# 利用旅程 AI {#concept_dsh_1ry_wfb}

此用例将向您展示如何利用疲劳得分，以避免在您的历程中过度吸引客户。

>[!NOTE]
>
>仅使用[Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html)的客户才能使用预测性疲劳得分功能。

## 配置事件 {#section_ptb_ws1_ffb}

按照[此页面](../event/about-events.md)中描述的步骤操作。

## 配置数据源 {#section_o3n_4yy_wfb}

执行以下步骤以选择内置数据源中的疲劳分数字段：

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Data Sources]**&#x200B;选项卡，然后选择内置的Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 检查是否选择了用例所需的字段。
1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**，选择&#x200B;**[!UICONTROL Profiles]**&#x200B;模型并添加&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;和&#x200B;**[!UICONTROL fatigueScore]**&#x200B;字段（位于&#x200B;_journeyAI > emailScore > fatigue_&#x200B;下）。

   ![](../assets/journeyuc3_1.png)

1. 单击 **[!UICONTROL Save]**。

## 构建历程 {#section_uzm_pyy_wfb}

要创建、验证和发布历程，请按照[此页面](../building-journeys/journey.md)中描述的步骤操作。

在我们的用例中，我们将利用&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;字段。 您还可以使用&#x200B;**[!UICONTROL fatigueScore]**&#x200B;字段。

执行以下步骤以利用历程中的疲劳级别：

1. 在历程中添加事件和条件。

   ![](../assets/journeyuc2_14.png)

1. 选择 **[!UICONTROL Data Source Condition]** 类型，然后在 **[!UICONTROL Expression]** 字段中单击。

   ![](../assets/journeyuc3_2.png)

1. 使用简单的表达式编辑器，查找&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;字段（_ExperiencePlatformDataSource > JourneyAIScores >用户档案> journeyAI > emailScore > fatigue_），将其放到右侧并创建以下条件：&quot;fatigueLevel等于&quot;Low&quot;。 单击 **[!UICONTROL Ok]**。

   ![](../assets/journeyuc3_3.png)

   高级表达式为：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在条件中，为中等和高疲劳级别创建其他两个路径。

   ![](../assets/journeyuc3_4.png)

1. 现在，您可以为每个疲劳级别添加不同的操作。

   ![](../assets/journeyuc3_5.png)
