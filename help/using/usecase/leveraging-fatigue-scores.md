---
product: adobe campaign
title: 利用疲劳分数
description: 瞭解如何在歷程中運用疲勞分數
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 12%

---


# 利用旅程 AI {#concept_dsh_1ry_wfb}

此使用案例將向您展示如何運用疲勞分數，以避免在您的歷程中過度向客戶提供請求。

>[!NOTE]
>
>預測性疲勞分數功能僅適用於使用 [Adobe Experience Platform資料聯結器](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## 配置事件 {#section_ptb_ws1_ffb}

請依照中所述的步驟操作 [此頁面](../event/about-events.md).

## 配置数据源 {#section_o3n_4yy_wfb}

執行以下步驟，在內建資料來源中選取疲勞分數欄位：

1. 在功能表窗格中，選取 **[!UICONTROL Admin]**. 在 **[!UICONTROL Data sources]** 部分中，单击 **[!UICONTROL Manage]**。
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 檢查是否選取了使用案例所需的欄位。
1. 按一下 **[!UICONTROL Add a New Field Group]**，選取 **[!UICONTROL Profiles]** 模型並新增 **[!UICONTROL fatigueLevel]** 和 **[!UICONTROL fatigueScore]** 欄位(在 _journeyAI > emailScore >疲勞_)。

   ![](../assets/journeyuc3_1.png)

1. 单击 **[!UICONTROL Save]**。

## 构建历程 {#section_uzm_pyy_wfb}

若要建立、驗證和發佈歷程，請遵循中所述的步驟 [此頁面](../building-journeys/journey.md).

在我們的使用案例中，我們運用 **[!UICONTROL fatigueLevel]** 欄位。 您也可以使用 **[!UICONTROL fatigueScore]** 欄位。

執行以下步驟，在您的歷程中運用疲勞層級：

1. 在您的歷程中新增事件和條件。

   ![](../assets/journeyuc2_14.png)

1. 选择 **[!UICONTROL Data Source Condition]** 类型，然后在 **[!UICONTROL Expression]** 字段中单击。

   ![](../assets/journeyuc3_2.png)

1. 使用簡單運算式編輯器，尋找 **[!UICONTROL fatigueLevel]** 欄位(_ExperiencePlatformDataSource > JourneyAIScores >設定檔> journeyAI > emailScore >疲勞_)，將其拖曳至右側並建立下列條件：「fatigueLevel等於「Low」。 单击 **[!UICONTROL Ok]**。

   ![](../assets/journeyuc3_3.png)

   進階運算式為：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在條件中，為中和高疲勞等級建立另外兩個路徑。

   ![](../assets/journeyuc3_4.png)

1. 您現在可以為每個疲勞層級新增不同的動作。

   ![](../assets/journeyuc3_5.png)
