---
product: adobe campaign
solution: Journey Orchestration
title: 创建测试用户档案
description: '了解测试用户档案创建 '
translation-type: tm+mt
source-git-commit: ccfe8d4d3eb8bf59d6dfd14eeb9f02578a09776f
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 2%

---


# 创建测试用户档案{#create-test-profiles}

在旅程中使用测试模式时，需要测试用户档案。 要了解如何使用测试模式，请参阅[本节](../building-journeys/testing-the-journey.md)。

在Adobe Experience Platform中创建测试用户档案有不同的方法。 在本文档中，我们侧重于两种方法：上传[csv文件](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)并使用[API调用](../building-journeys/creating-test-profiles.md#create-test-profiles-api)。 您还可以在数据集中上传json文件，请参阅[数据摄取文档](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)。

这些导入方法还允许您更新用户档案属性。 这样，您可以将现有用户档案转换为测试用户档案。 只需使用类似的文件或API调用，并且只包含值为“true”的“testProfile”字段。

创建测试用户档案与在Adobe Experience Platform中创建常规用户档案类似。 有关详细信息，请参阅[实时客户用户档案文档](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)。

## 先决条件{#test-profile-prerequisites}

为了能够创建用户档案，您首先需要在Adobe Experience Platform中创建模式和数据集。

首先，您需要&#x200B;**创建模式**。 按照以下步骤操作：

1. 在Adobe Experience Platform中，单击左侧菜单中的&#x200B;**[!UICONTROL Schemas]**。
   ![](../assets/test-profiles-0.png)
1. 单击右上角的&#x200B;**[!UICONTROL Create schema]**，然后选择模式类型，例如&#x200B;**[!UICONTROL XDM Individual Profile]**。
   ![](../assets/test-profiles-1.png)
1. 为模式选择名称。
1. 在&#x200B;**[!UICONTROL Mixins]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。
   ![](../assets/test-profiles-1-bis.png)
1. 选择适当的混音。 确保添加&#x200B;**[!UICONTROL Profile test details]**&#x200B;混音。 单击 **[!UICONTROL Add mixin]**.
   ![](../assets/test-profiles-1-ter.png)
混音的列表显示在模式概述屏幕上。

   ![](../assets/test-profiles-2.png)
1. 在字段列表中，单击要定义为主标识的字段。
   ![](../assets/test-profiles-3.png)
1. 在&#x200B;**[!UICONTROL Field properties]**&#x200B;右面板中，检查&#x200B;**[!UICONTROL Identity]**&#x200B;和&#x200B;**[!UICONTROL Primary Identity]**&#x200B;选项并选择命名空间。 如果希望主标识是电子邮件地址，请选择&#x200B;**[!UICONTROL Email]**&#x200B;命名空间。 单击 **[!UICONTROL Apply]**.
   ![](../assets/test-profiles-4.png)
1. 选择模式并启用&#x200B;**[!UICONTROL Schema properties]**&#x200B;中的&#x200B;**[!UICONTROL Profile]**选项。
   ![](../assets/test-profiles-5.png)
1. 单击 **[!UICONTROL Save]**.

>[!NOTE]
>
>有关创建模式的详细信息，请参阅[ XDM文档](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites)。

然后，您需要&#x200B;**创建要导入用户档案的数据集**。 按照以下步骤操作：

1. 在Adobe Experience Platform中，单击左菜单中的&#x200B;**[!UICONTROL Datasets]**，然后单击&#x200B;**[!UICONTROL Create dataset]**。
   ![](../assets/test-profiles-6.png)
1. 选择&#x200B;**[!UICONTROL Create dataset from schema]**。
   ![](../assets/test-profiles-7.png)
1. 选择之前创建的模式，然后单击&#x200B;**[!UICONTROL Next]**。
   ![](../assets/test-profiles-8.png)
1. 选择一个名称，然后单击&#x200B;**[!UICONTROL Finish]**。
   ![](../assets/test-profiles-9.png)
1. 启用&#x200B;**[!UICONTROL Profile]**选项。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 有关创建数据集的详细信息，请参阅[目录服务文档](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)。

## 使用csv文件{#create-test-profiles-csv}创建测试用户档案

在Adobe Experience Platform中，可以通过将包含不同用户档案字段的csv文件上载到数据集中来创建用户档案。 这是最简单的方法。

1. 使用电子表格软件创建一个简单的csv文件。
1. 为每个需要的字段添加一列。 确保添加主标识字段（上例中为“personID”）和设置为“true”的“testProfile”字段。
   ![](../assets/test-profiles-11.png)
1. 每个用户档案添加一行，并填写每个字段的值。
   ![](../assets/test-profiles-12.png)
1. 将电子表格另存为csv文件。 确保逗号用作分隔符。
1. 在Adobe Experience Platform中，单击左侧菜单中的&#x200B;**[!UICONTROL Workflows]**。
   ![](../assets/test-profiles-14.png)
1. 选择&#x200B;**[!UICONTROL Map CSV to XDM schema]**，然后单击&#x200B;**[!UICONTROL Launch]**。
   ![](../assets/test-profiles-16.png)
1. 选择要将用户档案导入的数据集。 单击 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-17.png)
1. 单击&#x200B;**[!UICONTROL Choose files]**&#x200B;并选择您的csv文件。 上载文件时，单击&#x200B;**[!UICONTROL Next]**。
   ![](../assets/test-profiles-18.png)
1. 将源csv字段映射到模式字段，然后单击&#x200B;**[!UICONTROL Finish]**。
   ![](../assets/test-profiles-19.png)
1. 数据导入开始。 状态将从&#x200B;**[!UICONTROL Processing]**&#x200B;移动到&#x200B;**[!UICONTROL Success]**。 单击右上方的&#x200B;**[!UICONTROL Preview data set]**。
   ![](../assets/test-profiles-20.png)
1. 检查测试用户档案是否已正确添加。
   ![](../assets/test-profiles-21.png)

将添加测试用户档案，现在可在测试旅程时使用。 请参阅[此章节](../building-journeys/testing-the-journey.md) 。
>[!NOTE]
>
> 有关csv导入的详细信息，请参阅[数据摄取文档](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)。

## 使用API调用创建测试用户档案{#create-test-profiles-api}

您还可以通过API调用创建测试用户档案。 请参阅此[页面](https://docs.adobe.com/content/help/zh-Hans/experience-platform/profile/home.html)。

必须使用包含“用户档案测试详细信息”混音的用户档案模式。 testProfile标志是此混音的一部分。

创建用户档案时，请确保传递值：testProfile = true。

请注意，您还可以更新现有用户档案以将其testProfile标志更改为“true”。

以下是用于创建测试用户档案的API调用示例：

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

