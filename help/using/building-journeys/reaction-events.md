---
product: adobe campaign
title: 回應事件
description: 瞭解反應事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 2%

---

# 反应事件 {#section_dhx_gss_dgb}

在浮動視窗中可用的不同事件活動中，您會找到內建的 **[!UICONTROL Reactions]** 事件。 此活動可讓您對追蹤資料做出反應，這些資料與相同歷程中透過電子郵件、簡訊或推播活動傳送的訊息有關。 此資訊來自Adobe Campaign Standard中的交易式傳訊。 我們會在與Adobe Experience Platform共用此資訊時即時擷取該資訊。 對於推播通知，您可以對點選、傳送或失敗的訊息做出反應。 對於SMS訊息，您可以對已傳送或失敗的訊息做出反應。 對於電子郵件，您可以對點選、傳送、開啟或失敗的訊息做出反應。

您也可以使用此機制，在訊息沒有反應時執行動作。 若要這麼做，請建立與反應活動平行的第二個路徑，並新增等待活動。 如果在等待活動中定義的期間內沒有反應，將選擇第二個路徑。 例如，您可以選擇傳送後續追蹤訊息。

請注意，您只能在畫布中使用回應活動，如果之前有電子郵件、推播或簡訊活動。

另請參閱 [關於動作活動](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

以下是設定反應事件的不同步驟：

1. 新增 **[!UICONTROL Label]** 以作出反應。 此步骤是可选的。
1. 從下拉式清單中，選取您要回應的動作活動。 您可以選取位於路徑先前步驟中的任何動作活動。
1. 根據您選取的動作（電子郵件、簡訊或推播通知），選擇您要回應的內容。
1. 您可以定義事件逾時（40秒至30天之間）和逾時路徑。 這將為未在定義的期間內回應的個人建立第二個路徑。 測試使用反應事件的歷程時，測試模式 **[!UICONTROL Wait time]** 預設值及最小值為40秒。 请参阅[此小节](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>反應事件適用於Adobe Campaign Standard，無論其部署在AWS還是Azure伺服器上。
>
>反應事件無法追蹤發生在不同歷程中的電子郵件、簡訊或推播動作。
>
>反應事件會追蹤「已追蹤」型別連結的點按(請參閱此 [頁面](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls))。 未考慮取消訂閱和映象頁面連結。

>[!IMPORTANT]
>
>電子郵件使用者端（例如Gmail）允許影像封鎖。 系統會使用電子郵件中包含的0畫素影像來追蹤電子郵件開啟次數。 如果影像遭到封鎖，則不會將電子郵件開啟次數列入考量。
