---
product: adobe campaign
title: 配置数据源
description: 瞭解如何設定歷程進階使用案例的資料來源
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# 配置数据源 {#concept_vml_hdy_w2b}

在我們的使用案例中，我們希望對訊息使用個人化資料。 我們還需要檢查該人士是否為忠誠會員，且在過去24小時內未與其聯絡。 此資訊儲存在即時客戶設定檔資料庫中。 此 **技術使用者** 需要設定Adobe Experience Platform資料來源以擷取這些欄位。

有關資料來源設定的其他資訊，請參閱 [此頁面](../datasource/about-data-sources.md).

1. 在功能表窗格中，選取 **[!UICONTROL Admin]**. 在 **[!UICONTROL Data sources]** 部分中，单击 **[!UICONTROL Manage]**。
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在預先設定的群組欄位中，檢查是否已選取下列欄位：

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail >地址_

1. 按一下 **[!UICONTROL Add a New Field Group]**，選取 **[!UICONTROL Profiles]** 結構描述並新增 **熟客會員** 條件欄位。 此 **熟客會員** 欄位是自訂欄位，已在XDM中新增：「_customer > marlton > loyaltyMember」

   ![](../assets/journeyuc2_6.png)

1. 按一下 **[!UICONTROL Add a New Field Group]**，選取 **[!UICONTROL ExperienceEvent]** 結構描述，並根據指定時段內傳送的訊息數，選擇條件所需的欄位： _timestamp_ 日期和 _directMarketing >傳送>值_ （已傳送的訊息數）。

   ![](../assets/journeyuc2_7.png)

1. 单击 **[!UICONTROL Save]**。

我們還需要檢查客人在飯店訂房系統中是否有預訂。 此 **技術使用者** 需要設定第二個資料來源來擷取此欄位。

1. 在資料來源清單中，按一下 **[!UICONTROL Add]** 以新增外部資料來源，定義與您的飯店訂房系統的連線。

   ![](../assets/journeyuc2_9.png)

1. 輸入資料來源和外部服務URL的名稱，例如： _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >出于安全原因，我们强烈建议使用 HTTPS。

1. 根据外部服务配置以配置身份验证：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或&#x200B;**[!UICONTROL API key]**。在我們的範例中，我們為型別選擇「基本」，並指定API呼叫的使用者名稱和密碼。

   ![](../assets/journeyuc2_10.png)

1. 按一下 **[!UICONTROL Add a New Field Group]** 以定義要擷取的資訊和API引數。 在我們的範例中，只有一個引數(id)，因此我們需要建立一個包含下列資訊的欄位群組：

   * **[!UICONTROL Method]**：选择 POST 或 GET 方法。在我们的示例中，我们选择 GET 方法。
   * **[!UICONTROL Response Payload]**：按一下 **[!UICONTROL Payload]** 欄位並貼上裝載的範例。 验证字段类型是否正确。每次调用 API 时，系统将检索有效负载示例中包含的所有字段。在我們的範例中，裝載僅包含預訂狀態：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**：輸入與用於識別每個客戶的金鑰對應的引數，在我們的範例中為「id」。 此引數的值將在歷程中定義。

   ![](../assets/journeyuc2_11.png)

1. 单击 **[!UICONTROL Save]**。

   資料來源現已設定完畢，可隨時用於您的歷程。
