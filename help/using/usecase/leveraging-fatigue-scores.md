---
title: 利用疲劳分数
description: 了解如何在旅程中利用疲劳分数
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


# 利用疲劳分数 {#concept_dsh_1ry_wfb}

此使用案例将向您展示如何利用疲劳分数来避免在旅程中过度吸引客户。

>[!CAUTION]
>
>预测疲劳分数功能仅适用于使用Adobe Campaign Standard Data service功能的客户。

## 配置活动 {#section_ptb_ws1_ffb}

按照中所述的步骤操作 [](../event/about-events.md)。

## 配置数据源 {#section_o3n_4yy_wfb}

执行以下步骤以选择内置数据源中的疲劳分数字段：

1. 在顶部菜单中，单击选 **[!UICONTROL Data Sources]**项卡，然后选择内置Experience Platform数据源。

   ![](../assets/journey23.png)

1. 检查是否已选择用例所需的字段。
1. 单 **[!UICONTROL Add a New Field Group]**击，选择模**[!UICONTROL Profiles]** 型并添加和字段(在 **[!UICONTROL fatigueLevel]**journeyAI > emailScore > fatigue**[!UICONTROL fatigueScore]**__&#x200B;下)。

   ![](../assets/journeyuc3_1.png)

1. 单击 **[!UICONTROL Save]**.

## 构建旅程 {#section_uzm_pyy_wfb}

要创建、验证和发布旅程，请按照中所述的步骤操作 [](../building-journeys/journey.md)。

在我们的使用案例中，我们利用了这个 **[!UICONTROL fatigueLevel]**领域。 您还可以使用该**[!UICONTROL fatigueScore]** 字段。

执行以下步骤以利用旅程中的疲劳程度：

1. 在旅程中添加活动和条件。

   ![](../assets/journeyuc2_14.png)

1. 选择类 **[!UICONTROL Data Source Condition]**型，然后单击字**[!UICONTROL Expression]** 段。

   ![](../assets/journeyuc3_2.png)

1. 使用简单的表达式编辑器，查找字 **[!UICONTROL fatigueLevel]**段(_ExperiencePlatformDataSource > JourneyAIScores > Profile > journeyAI > emailScore > fatigue_)，将其放到右侧并创建以下条件：“fatuyLevel”等于“Low”。 单击**[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   高级表达式为：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在该条件下，为中高疲劳水平创建另外两条路径。

   ![](../assets/journeyuc3_4.png)

1. 您现在可以为每个疲劳级别添加不同的操作。

   ![](../assets/journeyuc3_5.png)
