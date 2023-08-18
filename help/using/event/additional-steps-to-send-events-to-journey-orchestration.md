---
product: adobe campaign
title: 将事件发送到Journey Orchestration的其他步骤
description: 了解将事件发送到Journey Orchestration的其他步骤
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# 将事件发送到的其他步骤 [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>创建事件时， [!DNL Journey Orchestration] 自动为此事件生成ID。 推送事件的系统不应生成ID，它应使用有效负载预览中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

配置要发送到的事件 **[!UICONTROL Streaming Ingestion APIs]** 并用于 [!DNL Journey Orchestration]，您需要执行以下步骤：

1. 从Adobe Experience Platform API获取入口URL(请参阅 [流式引入API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hans))。
1. 从的有效负载预览中复制有效负载，位置在 **[!UICONTROL Event]** 菜单。 请参阅[此页](../event/defining-the-payload-fields.md)。

然后，您需要配置数据系统，以使用您复制的有效负载将事件推送到流式引入API：

1. 设置对流式引入API URL的POSTAPI调用（称为入口）。
1. 使用您复制过的有效负载 [!DNL Journey Orchestration] 在流摄取API的API调用的正文（“数据部分”）中。 有关示例，请参阅下文
1. 确定从何处获取有效负载中存在的所有变量。 示例：如果事件应传递地址，则粘贴的有效负载将显示“address”：“string”。 “string”应替换为自动填充正确值的变量，即向其发送消息的人员的电子邮件。 请注意，在有效负载预览中，在 **[!UICONTROL Header]** 部分，我们将自动填写许多预期有助于您完成工作的值。
1. 选择“application/json”作为主体类型。
1. 使用键“x-gw-ims-org-id”在标头中传递您的IMS组织ID。 对于值，请使用您的IMS组织ID (&quot;XXX@AdobeOrg&quot;)。

以下是流摄取API事件的示例：

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

为了便于识别粘贴“数据”部分的位置，您可以使用JSON可视化工具，例如 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

要排除流摄取API故障，请参阅此 [页面](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
