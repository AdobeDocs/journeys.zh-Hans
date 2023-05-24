---
product: adobe campaign
title: 更改属性
description: 瞭解如何變更屬性
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 1%

---

# 更改属性 {#concept_prq_wqt_52b}

按一下右上方的鉛筆圖示，即可存取歷程的屬性。

您可以變更歷程名稱、新增說明、允許重新進入、選擇開始和結束日期並定義 **[!UICONTROL Timeout and error]** 持續時間（如果您是管理員）。

若為即時歷程，此畫面會顯示發佈日期和發佈歷程的使用者名稱。

此 **複製技術細節** 可讓您複製支援團隊可用於疑難排解的歷程相關技術資訊。 已複製下列資訊：JourneyVersion UID、OrgID、orgName、sandboxName、lastDeployedBy、lastDeployedAt。

![](../assets/journey32.png)

## 入口{#entrance}

依預設，新歷程允許重新進入。 您可以取消勾選「一次性」歷程的選項，例如，如果您想要在某人進入商店時提供一次性禮物。 在這種情況下，您不希望客戶能夠重新進入歷程並再次收到選件。

當歷程「結束」時，會有狀態 **[!UICONTROL Closed (no entrance)]**. 歷程將停止讓新個人進入歷程。 已在歷程中的人員將正常完成歷程。

在預設全域逾時30天後，歷程將切換為 **已完成** 狀態。 请参阅此[部分](#global_timeout)。

## 歷程活動中的逾時和錯誤 {#timeout_and_error}

編輯動作或條件活動時，您可以定義替代路徑，以防錯誤或逾時。 如果處理詢問協力廠商系統的活動超過歷程屬性中定義的逾時期間(**[!UICONTROL Timeout and  error]** 欄位)，則會選擇第二個路徑來執行潛在的遞補動作。

授權值介於1到30秒之間。

建議您最好定義一個非常簡短的 **[!UICONTROL Timeout and error]** 值(如果您的歷程對時間敏感（例如：對個人的即時位置做出反應），因為您的動作無法延遲超過幾秒鐘。 如果您的歷程不太敏感，您可以使用較長的值，讓系統有更多時間呼叫，以傳送有效回應。

[!DNL Journey Orchestration] 也會使用全域逾時。 請參閱 [下一節](#global_timeout).

## 全域歷程逾時 {#global_timeout}

除了 [逾時](#timeout_and_error) 在歷程活動中使用，也會有全域歷程逾時，此逾時不會顯示在介面中且無法變更。 此逾時將在個人進入後30天，停止歷程中的進度。 這表示個人的歷程不能持續超過30天。 在30天逾時期間後，個人的資料會被刪除。 在逾時期間結束時仍在歷程中流動的個人將停止，並將他們視為報告中的錯誤。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不會直接回應隱私權選擇退出、存取或刪除請求。 不過，全域逾時可確保個人在任何歷程中的逗留時間不會超過30天。

由於30天歷程逾時，當歷程重新進入遭到禁止時，我們無法確保重新進入封鎖會運作超過30天。 事實上，由於我們移除了在進入歷程30天後進入歷程之人員的所有資訊，因此我們無法得知該人員先前已進入（超過30天前）。

## 時區和設定檔時區 {#timezone}

時區在歷程層級定義。

您可以輸入固定時區，或使用Adobe Experience Platform設定檔來定義歷程時區。

如需時區管理的詳細資訊，請參閱 [此頁面](../building-journeys/timezone-management.md).
