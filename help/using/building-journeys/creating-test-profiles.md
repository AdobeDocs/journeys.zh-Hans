---
product: adobe campaign
title: 建立測試設定檔
description: 瞭解如何建立測試設定檔
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 5%

---

# 创建测试用户档案 {#create-test-profiles}

在歷程中使用測試模式時，需要測試設定檔。 若要瞭解如何使用測試模式，請參閱 [本節](../building-journeys/testing-the-journey.md).

在Adobe Experience Platform中建立測試設定檔有不同的方式。 在本檔案中，我們著重介紹兩種方法：上傳 [csv檔案](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) 和使用 [API呼叫](../building-journeys/creating-test-profiles.md#create-test-profiles-api). 您也可以在資料集中上傳json檔案，請參閱 [資料擷取檔案](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

這些匯入方法也可讓您更新設定檔屬性。 如此一來，您就可以將現有的設定檔轉換為測試設定檔。 只需使用類似的檔案或API呼叫，且僅包含值為「true」的「testProfile」欄位。

建立測試設定檔類似於在Adobe Experience Platform中建立一般設定檔。 如需詳細資訊，請參閱 [即時客戶個人檔案檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans).

## 先决条件{#test-profile-prerequisites}

為了能夠建立設定檔，您首先需要在Adobe Experience Platform中建立結構描述和資料集。

首先，您需要 **建立結構描述**. 执行以下步骤：

1. 在Adobe Experience Platform中，按一下 **[!UICONTROL Schemas]**，位於左側功能表中。
   ![](../assets/test-profiles-0.png)
1. 按一下 **[!UICONTROL Create schema]**，然後選取結構描述型別，例如 **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. 為您的結構描述選擇一個名稱。
1. 在 **[!UICONTROL Mixins]** 部分中，单击 **[!UICONTROL Add]**。
   ![](../assets/test-profiles-1-bis.png)
1. 選取適當的Mixin。 請務必新增 **[!UICONTROL Profile test details]** mixin. 单击 **[!UICONTROL Add mixin]**。
   ![](../assets/test-profiles-1-ter.png)
Mixin清單會顯示在架構概觀畫面上。

   ![](../assets/test-profiles-2.png)
1. 在欄位清單中，按一下要定義為主要身分的欄位。
   ![](../assets/test-profiles-3.png)
1. 在 **[!UICONTROL Field properties]** 右側面板，檢查 **[!UICONTROL Identity]** 和 **[!UICONTROL Primary Identity]** 選項並選取名稱空間。 如果您希望主要身分識別是電子郵件地址，請選擇 **[!UICONTROL Email]** 名稱空間。 单击 **[!UICONTROL Apply]**。
   ![](../assets/test-profiles-4.png)
1. 選取結構描述並啟用 **[!UICONTROL Profile]** 中的選項 **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>如需建立結構的詳細資訊，請參閱 [XDM檔案](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

然後您需要 **建立資料集** 將匯入設定檔的位置。 执行以下步骤：

1. 在Adobe Experience Platform中，按一下 **[!UICONTROL Datasets]**，然後按一下「 」 **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. 選擇 **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. 選取先前建立的結構描述，然後按一下 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. 選擇名稱，然後按一下 **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. 啟用 **[!UICONTROL Profile]** 選項。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 如需建立資料集的詳細資訊，請參閱 [目錄服務檔案](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## 使用csv檔案建立測試設定檔{#create-test-profiles-csv}

在Adobe Experience Platform中，您可以上傳包含不同設定檔欄位的csv檔案來建立設定檔。 這是最簡單的方法。

1. 使用試算表軟體建立簡單的csv檔案。
1. 為每個所需欄位新增一欄。 請務必新增主要身分欄位（以上範例中為「personID」），並將「testProfile」欄位設為「true」。
   ![](../assets/test-profiles-11.png)
1. 為每個設定檔新增一行，並填入每個欄位的值。
   ![](../assets/test-profiles-12.png)
1. 將試算表儲存為csv檔案。 請務必使用逗號做為分隔符號。
1. 在Adobe Experience Platform中，按一下 **[!UICONTROL Workflows]**，位於左側功能表中。
   ![](../assets/test-profiles-14.png)
1. 選擇 **[!UICONTROL Map CSV to XDM schema]**，然後按一下 **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. 選取您要將設定檔匯入的資料集。 单击 **[!UICONTROL Next]**。
   ![](../assets/test-profiles-17.png)
1. 按一下 **[!UICONTROL Choose files]** 並選取您的csv檔案。 上傳檔案時，按一下 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. 將來源csv欄位對應到結構描述欄位，然後按一下 **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. 資料匯入隨即開始。 狀態將移自 **[!UICONTROL Processing]** 至 **[!UICONTROL Success]**. 按一下 **[!UICONTROL Preview data set]**，位於右上方。
   ![](../assets/test-profiles-20.png)
1. 檢查測試設定檔是否已正確新增。
   ![](../assets/test-profiles-21.png)

您的測試設定檔已新增，現在可用於測試歷程。 请参阅[此小节](../building-journeys/testing-the-journey.md)。
>[!NOTE]
>
> 如需csv匯入的詳細資訊，請參閱 [資料擷取檔案](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## 使用API呼叫建立測試設定檔{#create-test-profiles-api}

您也可以透過API呼叫建立測試設定檔。 请参阅此[页面](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)。

您必須使用包含「設定檔測試詳細資料」mixin的設定檔結構描述。 testProfile旗標是此mixin的一部分。

建立設定檔時，請務必傳遞值： testProfile = true。

請注意，您也可以更新現有的設定檔，將其testProfile標幟變更為「true」。

以下是為建立測試設定檔而進行API呼叫的範例：

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
