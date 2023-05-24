---
product: adobe campaign
title: 选择命名空间
description: 瞭解如何選取名稱空間
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 选择命名空间 {#concept_ckb_3qt_52b}

名稱空間可讓您定義用來識別與事件相關聯之人員的金鑰型別。 其設定是選用的。 如果您想要在歷程中擷取其他資訊，則需要使用 [即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans). 如果您只使用來自協力廠商系統、透過自訂資料來源的資料，則不需要名稱空間定義。

您可以使用其中一個預先定義的名稱空間，或使用「身分識別名稱空間」服務建立新的名稱空間。 請參閱此 [頁面](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans).

如果您選取具有主要身分的結構描述，則 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 欄位會預先填入。 如果沒有定義身分，我們會選取 _identityMap > id_ 作為主索引鍵。 之後，您必須選取名稱空間，且金鑰將會預先填滿(在 **[!UICONTROL Namespace]** 欄位)，使用 _identityMap > id_.

選取欄位時，會標籤主要身分欄位。

![](../assets/primary-identity.png)


從下拉式清單中選取名稱空間。

![](../assets/journey17.png)

每個歷程只允許一個名稱空間。 如果您在同一個歷程中使用數個事件，則它們需要使用相同的名稱空間。 请参阅[此页](../building-journeys/journey.md)。
