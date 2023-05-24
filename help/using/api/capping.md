---
product: adobe campaign
title: 設定API說明上限
description: 深入瞭解上限API。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 32%

---


# 使用上限API {#work}

上限API可幫助您建立、設定和監控您的上限設定。

## 設定API說明上限

| 方法 | 路径 | 描述 |
|---|---|---|
| [!DNL POST] | list/endpointConfig | 取得端點上限設定清單 |
| [!DNL POST] | /endpointConfigs | 建立端點上限設定 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 部署端點上限設定 |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | 取消部署端點上限設定 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 檢查是否可以部署端點上限設定 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 更新端點上限設定 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 擷取端點上限設定 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 刪除端點上限設定 |

建立或更新設定時，會自動執行檢查以確保語法和裝載的完整性。
如果發生某些問題，作業會傳回警告或錯誤，以協助您更正設定。

## 端點設定

以下是端點設定的基本結構：

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### 示例：

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## 警告和錯誤

當 **canDeploy** 方法呼叫，該程式會驗證設定並傳回由其唯一ID識別的驗證狀態，其形式為：

```
"ok" or "error"
```

可能的錯誤包括：

* **ERR_ENDPOINTCONFIG_100**：上限設定：遺失或無效的url
* **ERR_ENDPOINTCONFIG_101**：上限設定：格式錯誤的url
* **ERR_ENDPOINTCONFIG_102**：上限設定：格式錯誤的url：host：port中不允許url中的wildchar
* **ERR_ENDPOINTCONFIG_103**：上限設定：遺失HTTP方法
* **ERR_ENDPOINTCONFIG_104**：上限設定：未定義任何通話分級
* **ERR_ENDPOINTCONFIG_107**：上限設定：無效的最大呼叫計數(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**：上限設定：無效的最大呼叫計數(periodInMs)
* **ERR_ENDPOINTCONFIG_111**：上限設定：無法建立端點設定：無效的承載
* **ERR_ENDPOINTCONFIG_112**：上限設定：無法建立端點設定：預期JSON裝載
* **ERR_AUTHORING_ENDPOINTCONFIG_1**：無效的服務名稱 `<!--<given value>-->`：必須為「dataSource」或「action」

可能的警告是：

**ERR_ENDPOINTCONFIG_106**：上限設定：未定義最大HTTP連線：預設無限制

## 用例

在本節中，您將找到五個主要使用案例，您可以執行這些案例來管理您的上限設定，位置在 [!DNL Journey Orchestration].

为帮助您进行测试和配置，可点击[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)获取 Postman 集合。

此“Postman 集合”已设置为通过 __[Adobe I/O 控制台的集成](https://console.adobe.io/integrations) > 试用 > 为 Postman 下载__&#x200B;共享 Postman 变量集合，它会使用选定的集成值生成 Postman 环境文件。

下载并上传到 Postman 后，您需要添加三个变量：`{JO_HOST}`、`{BASE_PATH}` 和 `{SANDBOX_NAME}`。
* `{JO_HOST}`：[!DNL Journey Orchestration]网关 URL
* `{BASE_PATH}`：API 的入口点。值为“/authoring”
* `{SANDBOX_NAME}`：标头 **x-sandbox-name**（例如，“prod”），对应将执行 API 操作的沙盒名称。有关更多信息，请参阅[沙盒概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hans)。

在以下部分中，您将找到用于执行用例的 Rest API 调用排序列表。

使用案例n°1： **建立及部署新的上限設定**

1. list
1. create
1. candeploy
1. deploy

使用案例n°2： **更新和部署尚未部署的上限設定**

1. list
1. get
1. update
1. candeploy
1. deploy

使用案例n°3： **取消部署和刪除已部署的上限設定**

1. list
1. undeploy
1. delete

使用案例n°4： **刪除已部署的上限設定。**

在仅一个 API 调用中，您可以使用 forceDelete 参数取消部署和删除配置。
1. list
1. 删除，使用 forceDelete 参数

使用案例n°5： **更新已部署的上限設定**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
