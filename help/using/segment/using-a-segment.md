---
product: adobe campaign
title: 在条件中使用区段
description: 瞭解如何使用區段
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---

# 在条件中使用区段 {#using-a-segment}

本節說明如何在歷程條件中使用區段。 若要瞭解如何使用 **[!UICONTROL Segment qualification]** 歷程中的事件，請參閱此 [區段](../building-journeys/segment-qualification-events.md).

若要在歷程條件中使用區段，請遵循下列步驟：

1. 開啟歷程，拖放 **[!UICONTROL Condition]** 活動並選擇 **資料來源條件**.
   ![](../assets/journey47.png)

1. 按一下 **[!UICONTROL Add a path]** 每個需要的額外路徑。 對於每個路徑，按一下 **[!UICONTROL Expression]** 欄位。

   ![](../assets/segment3.png)

1. 在左側，展開 **[!UICONTROL Segments]** 節點。 拖放您要用於條件的區段。 依預設，區段的條件為true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >只有具備下列條件的個人 **已實現** 和 **現有** 區段參與狀態會視為區段的成員。 如需如何評估區段的詳細資訊，請參閱 [Segment Service檔案](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

有關歷程條件以及如何使用簡單運算式編輯器的詳細資訊，請參閱 [條件活動](../building-journeys/condition-activity.md#about_condition).
