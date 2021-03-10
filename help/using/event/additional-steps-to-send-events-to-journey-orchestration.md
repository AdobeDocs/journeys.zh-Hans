---
product: adobe campaign
solution: Journey Orchestration
title: 将事件发送到Journey Orchestration的其他步骤
description: 了解将事件发送到Journey Orchestration的其他步骤
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 7%

---



# 将事件发送到[!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}的其他步骤

>[!NOTE]
>
>创建事件时，[!DNL Journey Orchestration]会自动生成此事件的ID。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

要将事件配置为发送到&#x200B;**[!UICONTROL Streaming Ingestion APIs]**&#x200B;并在[!DNL Journey Orchestration]中使用，您需要执行以下步骤：

1. 从Adobe Experience Platform API获取入口URL（请参阅[流摄取API](https://docs.adobe.com/content/help/zh-Hans/experience-platform/ingestion/streaming/overview.html)）。
1. 从&#x200B;**[!UICONTROL Event]**&#x200B;菜单中的有效负荷预览复制有效负荷。 请参阅[此页](../event/defining-the-payload-fields.md)。

然后，您需要配置使用您复制的有效负荷将事件推送到流摄取API的数据系统：

1. 设置对流摄取API URL（称为入口）的POSTAPI调用。
1. 使用您从对Streaming Ingestion API的API调用的正文（“数据部分”）中的[!DNL Journey Orchestration]复制的有效负荷。 有关示例，请参见下面
1. 确定在何处获取有效负荷中存在的所有变量。 示例：如果事件应传达地址，则粘贴的有效负荷将显示“地址”：“string”。 “string”应替换为将自动填充正确值（要向其发送消息的人员的电子邮件）的变量。 请注意，在有效负荷预览的&#x200B;**[!UICONTROL Header]**&#x200B;部分，我们会自动填充许多值，以便于您的工作。
1. 选择“application/json”作为正文类型。
1. 使用键“x-gw-ims-org-id”在标题中传递您的IMS组织ID。 对于该值，请使用您的IMS组织ID(“XXX@AdobeOrg”)。

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

为了便于确定粘贴“data”部件的位置，您可以使用JSON可视化工具，如[https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

要对流摄取API进行疑难解答，请参阅此[页面](https://docs.adobe.com/content/help/zh-Hans/experience-platform/ingestion/streaming/troubleshooting.html)。
