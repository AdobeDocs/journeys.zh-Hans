---
product: adobe campaign
title: 關於Campaign v7/v8整合
description: 瞭解Campaign v7/v8整合
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 13%

---

# 使用 Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

這項整合適用於Adobe Campaign Classic v7 （從21.1版開始）和Adobe Campaign v8。 它让您可以使用 Adobe Campaign 事务性消息传递功能发送电子邮件、推送通知和 SMS。

Journey Orchestration 实例和 Campaign 实例之间的连接是在配置时通过 Adobe 来设置的。

本頁面介紹端對端使用案例 [區段](../usecase/campaign-classic-use-case.md).

對於每個已設定的動作，歷程設計工具浮動視窗中都有動作活動可用。 请参阅此[章节](../building-journeys/using-adobe-campaign-classic.md)。

## 重要说明

* 無訊息限制。 我們根據目前的Campaign SLA，將可傳送的訊息數量上限設為每小時50,000封。 因此，Journey Orchestration應僅用於單一使用案例（個別事件，而非區段）。

* 您必須在要使用的每個範本的畫布上設定一個動作。 您需要為您要從Adobe Campaign使用的每個範本在Journey Orchestration中設定一個動作。

* 建議您使用針對這項整合而代管的專用訊息中心執行個體，以避免影響您可能進行的任何其他Campaign作業。 行銷伺服器可以是託管式或內部部署。 所需的版本編號為21.1版本候選版本或更新版本。

* 沒有驗證裝載或Campaign訊息是否正確。

* 促銷活動動作不可與區段資格事件搭配使用。

## 先决条件

在Campaign中，您需要建立並發佈交易式訊息及其相關事件。 請參閱 [Adobe Campaign檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

您可以依照以下模式，建置與每則訊息相對應的JSON裝載。 然後，當您在Journey Orchestration中設定動作時，會貼上此裝載（請參閱下文）

示例如下：

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **頻道**：為您的Campaign交易範本定義的管道
* **事件型別**：Campaign事件的內部名稱
* **ctx**：變數，根據您訊息中的個人化設定而定。

## 設定動作

在Journey Orchestration中，您需要為每個交易式訊息設定一個動作。 执行以下步骤：

1. 建立新動作。 请参阅此[章节](../action/action.md)。
1. 輸入名稱和說明。
1. 在 **動作型別** 欄位，選取 **Adobe Campaign Classic**.
1. 按一下 **裝載** 欄位並貼上與Campaign訊息相對應的JSON裝載範例。 聯絡Adobe以取得此裝載。
1. 視您想要在歷程畫布上對應欄位，將不同的欄位調整為靜態或變數。 某些欄位，例如電子郵件地址和個人化欄位(ctx)的管道引數，您可能想要定義為要在歷程內容中對應的變數。
1. 单击&#x200B;**保存**。

![](../assets/accintegration1.png)


