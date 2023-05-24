---
product: adobe campaign
title: 傳送事件給Journey Orchestration的其他步驟
description: 瞭解將事件傳送至Journey Orchestration的其他步驟
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# 將事件傳送至的其他步驟 [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>建立事件時， [!DNL Journey Orchestration] 自動產生此事件的ID。 推播事件的系統不應產生ID，而應使用有效負載預覽中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

若要設定要傳送至的事件 **[!UICONTROL Streaming Ingestion APIs]** 並將用於 [!DNL Journey Orchestration]，您必須遵循下列步驟：

1. 從Adobe Experience Platform API取得入口URL (請參閱 [串流擷取API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hans))。
1. 從中的裝載預覽複製裝載 **[!UICONTROL Event]** 功能表。 请参阅[此页](../event/defining-the-payload-fields.md)。

然後，您需要設定資料系統，使用您複製的裝載將事件推送至串流獲取API：

1. 設定串流獲取API URL的POSTAPI呼叫（稱為入口）。
1. 使用您複製自的裝載 [!DNL Journey Orchestration] 串流獲取API之API呼叫的內文（「資料區段」）中。 如需範例，請參閱下文
1. 決定從何處取得裝載中出現的所有變數。 範例：如果事件應該要傳達位址，貼上的裝載會顯示「address」：「string」。 「string」應取代為會自動填入正確值的變數，也就是傳送訊息的收件者電子郵件。 請注意，在裝載預覽中，在 **[!UICONTROL Header]** 章節，我們會自動填入許多值，以利您順利完成工作。
1. 選取「application/json」作為內文型別。
1. 使用索引鍵「x-gw-ims-org-id」在標題中傳遞您的IMS組織ID。 此值使用您的IMS組織ID (&quot;XXX@AdobeOrg&quot;)。

以下是串流擷取API事件的範例：

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

為方便您識別「資料」部分的貼上位置，您可以使用JSON視覺化工具，例如 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

若要疑難排解串流獲取API，請參閱此 [頁面](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
