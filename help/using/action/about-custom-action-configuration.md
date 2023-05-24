---
product: adobe campaign
title: 关于自定义操作配置
description: 瞭解如何設定自訂動作
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# 关于自定义操作配置 {#concept_sxy_bzs_dgb}

如果您使用協力廠商系統來傳送訊息，或是您想要的話 [!DNL Journey Orchestration] 若要將API呼叫傳送至協力廠商系統，您可以在此處設定其連線至 [!DNL Journey Orchestration]. 之後，技術使用者定義的自訂動作將可在您歷程的左側浮動視窗中使用，位於 **[!UICONTROL Action]** 類別(請參閱 [此頁面](../building-journeys/about-action-activities.md). 以下是一些您可以透過自訂動作連線的系統範例：Epsilon、Facebook、Adobe.io、Firebase等。

限制列於 [此頁面](../about/limitations.md).

在自訂動作引數中，您可以傳遞簡單的集合以及物件集合。 關於限制，請參閱 [此頁面](../usecase/collections.md#limitations). 另請注意，引數具有預期格式（例如：字串、小數等）。 您必須注意遵守這些預期的格式。 請參閱此 [使用案例](../usecase/collections.md).

以下是設定自訂動作所需的主要步驟：

1. 從 **[!UICONTROL Actions]** 清單，按一下 **[!UICONTROL Add]** 以建立新動作。 動作設定窗格會在畫面右側開啟。

   ![](../assets/custom2.png)

1. 輸入動作的名稱。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 為動作新增說明。 此步骤是可选的。
1. 使用此動作的歷程次數會顯示在 **[!UICONTROL Used in]** 欄位。 您可以按一下 **[!UICONTROL View journeys]** 按鈕來顯示使用此動作的歷程清單。
1. 定義不同的 **[!UICONTROL URL Configuration]** 引數。 请参阅[此页](../action/url-configuration.md)。
1. 設定 **[!UICONTROL Authentication]** 區段。 此設定與資料來源的設定相同。  请参阅[此小节](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定義 **[!UICONTROL Action parameters]**. 请参阅[此页](../action/defining-the-message-parameters.md)。
1. 单击 **[!UICONTROL Save]**。

   自訂動作現已設定完畢，且可供您在歷程中使用。 请参阅[此页](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在歷程中使用自訂動作時，大部分引數均為唯讀。 您只能修改 **[!UICONTROL Name]**， **[!UICONTROL Description]**， **[!UICONTROL URL]** 欄位和 **[!UICONTROL Authentication]** 區段。
