---
title: 将事件发送到旅程安排的其他步骤
description: 了解将事件发送到旅程安排的其他步骤
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---



# 将事件发送到旅程安排的其他步骤 {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>创建事件时，旅程安排会自动为此事件生成ID。 推送事件的系统不应生成ID，它应使用有效负荷预览中的可用ID。 请参见 [](../event/previewing-the-payload.md)。

要配置要发送到旅程安排中 **[!UICONTROL Streaming Ingestion APIs]** 的事件以及要在旅程安排中使用的集合，您需要执行以下步骤：

1. 从数据平台API获取入口URL(请参 [阅流摄取API](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/overview.html))。
1. 从菜单中的有效负荷预览复制有效 **[!UICONTROL Event]** 负荷。 请参见 [](../event/defining-the-payload-fields.md)。

然后，您需要配置使用您复制的有效负荷将事件推送到流摄取API的数据系统：

1. 设置对流摄取API URL（称为入口）的POST API调用。
1. 使用从API调用主体（“数据部分”）中的旅程编排复制到流摄取API的有效负荷。 请参见下面的示例
1. 确定从何处获取有效负荷中存在的所有变量。 示例：如果事件应传达地址，则粘贴的有效负荷将显示“地址”:“string”。 “string”应替换为将自动填充正确值（要向其发送消息的人员的电子邮件）的变量。 请注意，在有效负荷预览的一节中， **[!UICONTROL Header]** 我们会自动填充许多值，以便于您工作。
1. 选择“application/json”作为正文类型。
1. 使用键“x-gw-ims-org-id”在标题中传递您的IMS ORG ID。 对于该值，请使用您的IMS ORG ID(“XXX@AdobeOrg”)。

以下是Streaming Ingestion API事件的示例：

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

为便于识别粘贴“数据”部件的位置，您可以使用JSON可视化工具，如 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

要对流摄取API进行疑难解答，请参阅本 [页](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html)。
