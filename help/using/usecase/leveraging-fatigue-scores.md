---
product: adobe campaign
title: 利用疲劳分数
description: 了解如何在历程中利用疲劳分数
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# 利用历程人工智能 {#concept_dsh_1ry_wfb}

此用例将向您展示如何利用疲劳得分避免在您的历程中过度招徕客户。

>[!NOTE]
>
>预测疲劳得分功能仅适用于使用[Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html?lang=zh-Hans)的客户。

## 配置事件 {#section_ptb_ws1_ffb}

按照[此页面](../event/about-events.md)中描述的步骤操作。

## 配置数据源 {#section_o3n_4yy_wfb}

执行以下步骤以选择内置数据源中的疲劳得分字段：

1. 在菜单窗格中，选择&#x200B;**[!UICONTROL Admin]**。 在&#x200B;**[!UICONTROL Data sources]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Manage]**。
1. 选择内置的Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 检查是否选择了用例所需的字段。
1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**，选择&#x200B;**[!UICONTROL Profiles]**&#x200B;模型并添加&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;和&#x200B;**[!UICONTROL fatigueScore]**&#x200B;字段（在&#x200B;_journeyAI > emailScore > fatigue_&#x200B;下）。

   ![](../assets/journeyuc3_1.png)

1. 单击 **[!UICONTROL Save]**。

## 构建历程 {#section_uzm_pyy_wfb}

要创建、验证和发布历程，请按照[此页面](../building-journeys/journey.md)中描述的步骤操作。

在我们的用例中，我们使用的是&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;字段。 您还可以使用&#x200B;**[!UICONTROL fatigueScore]**&#x200B;字段。

执行以下步骤以在历程中利用疲劳级别：

1. 在历程中添加事件和条件。

   ![](../assets/journeyuc2_14.png)

1. 选择&#x200B;**[!UICONTROL Data Source Condition]**&#x200B;类型并单击&#x200B;**[!UICONTROL Expression]**&#x200B;字段。

   ![](../assets/journeyuc3_2.png)

1. 使用简单表达式编辑器，查找&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;字段(_ExperiencePlatformDataSource > JourneyAIScores > Profile > journeyAI > emailScore > fatigue_)，将其拖到右侧并创建以下条件：“fatigueLevel等于“Low”。 单击 **[!UICONTROL Ok]**。

   ![](../assets/journeyuc3_3.png)

   高级表达式为：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在条件中，为中和高疲劳级别创建另外两个路径。

   ![](../assets/journeyuc3_4.png)

1. 您现在可以为每个疲劳级别添加不同的操作。

   ![](../assets/journeyuc3_5.png)
