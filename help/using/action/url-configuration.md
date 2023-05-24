---
product: adobe campaign
title: URL 配置
description: 瞭解URL設定
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# URL 配置 {#concept_gbg_1f1_2gb}

設定自訂動作時，您需要定義下列專案 **[!UICONTROL URL Configuration]** 引數：

![](../assets/journeyurlconfiguration.png)

1. 在 **[!UICONTROL URL]** 欄位中，指定外部服務的URL：

   * 如果URL是靜態的，請在此欄位中輸入URL。

   * 如果URL包含動態路徑，請只輸入URL的靜態部分，即配置、主機、連線埠，以及（選擇性）路徑的靜態部分。

      示例：`https://xxx.yyy.com/somethingstatic/`

      將自訂動作新增至歷程時，您將指定URL的動態路徑。 [了解详情](../building-journeys/using-custom-actions.md)。
   >[!NOTE]
   >
   >基於安全考量，強烈建議您針對URL使用HTTPS配置。 我們不允許使用非公開的Adobe位址和IP位址。
   >
   >定義自訂動作時只允許預設連線埠：80代表http，443代表https。

1. 選取通話 **[!UICONTROL Method]**：它可以是以下任一值 **[!UICONTROL POST]** 或 **[!UICONTROL PUT]**.
1. 在 **[!UICONTROL Headers]** 區段，定義要傳送至外部服務之要求訊息的HTTP標頭：
   1. 若要新增標題欄位，請按一下 **[!UICONTROL Add a header field]**.
   1. 輸入頁首欄位的鍵。
   1. 若要設定索引鍵/值組的動態值，請選取 **[!UICONTROL Variable]**. 否則，請選取 **[!UICONTROL Constant]**.

      例如，對於時間戳記，您可以設定動態值。

   1. 如果您已選取 **[!UICONTROL Constant]**，然後輸入常數值。

      如果您已選取 **[!UICONTROL Variable]**，則會在將自訂動作新增至歷程時指定此變數。 [了解详情](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. 若要刪除標頭欄位，請指向標頭欄位並按一下 **[!UICONTROL Delete]** 圖示。
   此 **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 標頭欄位預設為設定。 您無法修改或刪除這些欄位。

   將自訂動作新增至歷程後，如果歷程處於草稿狀態，您仍可新增標題欄位至歷程。 如果您不想讓歷程受設定變更影響，請複製自訂動作，並將標題欄位新增到新的自訂動作。

   >[!NOTE]
   >
   >標頭會根據欄位剖析規則進行驗證。 [了解详情](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
