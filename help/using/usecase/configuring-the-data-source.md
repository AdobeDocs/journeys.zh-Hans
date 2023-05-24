---
product: adobe campaign
title: 配置数据源
description: 瞭解如何為歷程簡單使用案例設定資料來源
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 9%

---

# 配置数据源{#concept_ax3_bcy_w2b}

在我們的使用案例中，我們希望對訊息使用個人化資料。 我們還需要檢查這個人是不是女性。 此資訊儲存在即時客戶設定檔資料庫中。 此 **技術使用者** 需要檢查這些欄位是否在內建的Adobe Experience Platform資料來源中定義。

有關資料來源設定的其他資訊，請參閱 [此頁面](../datasource/about-data-sources.md).

1. 在功能表窗格中，選取 **[!UICONTROL Admin]**. 在 **[!UICONTROL Data sources]** 部分中，单击 **[!UICONTROL Manage]**。
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在欄位群組中，檢查是否已選取下列欄位：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人員>性別_
   * _personalEmail >地址_

1. 单击 **[!UICONTROL Save]**。

資料來源現已設定完畢，可隨時用於您的歷程。
