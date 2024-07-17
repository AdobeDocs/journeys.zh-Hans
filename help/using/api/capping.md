---
product: adobe campaign
title: API说明上限
description: 了解有关Capping API的更多信息。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 29%

---


# 使用上限API {#work}

上限API可帮助您创建、配置和监控上限配置。

## API说明上限

| 方法 | 路径 | 描述 |
|---|---|---|
| [!DNL POST] | list/endpointConfig | 获取端点上限配置的列表 |
| [!DNL POST] | /endpointConfigs | 创建端点上限配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 部署端点上限配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | 取消部署端点上限配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 检查是否可以部署端点上限配置 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 更新端点上限配置 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 检索端点上限配置 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 删除端点封顶配置 |

创建或更新配置时，将自动执行检查以确保语法和有效负载的完整性。
如果发生某些问题，该操作将返回警告或错误，以帮助您更正配置。

## 端点配置

以下是端点配置的基本结构：

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>**maxHttpConnections**&#x200B;参数是可选的。 它允许您限制Journey Optimizer将打开到外部系统的连接数。
>
>可以设置的最大值为400。 如果未指定任何内容，则系统可能会打开数千个连接，具体取决于系统的动态缩放情况。

### 示例：

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## 警告和错误

调用&#x200B;**canDeploy**&#x200B;方法时，进程将验证配置并返回由其唯一ID标识的验证状态：

```
"ok" or "error"
```

潜在的错误包括：

* **ERR_ENDPOINTCONFIG_100**：配置上限：缺少URL或无效的URL
* **ERR_ENDPOINTCONFIG_101**：上限配置：错误的url
* **ERR_ENDPOINTCONFIG_102**：上限配置：格式错误的url：主机：端口中不允许使用url中的通配符
* **ERR_ENDPOINTCONFIG_103**：上限配置：缺少HTTP方法
* **ERR_ENDPOINTCONFIG_104**：上限配置：未定义调用等级
* **ERR_ENDPOINTCONFIG_107**：上限配置：无效的最大调用计数(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**：上限配置：无效的最大调用计数(periodInMs)
* **ERR_ENDPOINTCONFIG_111**：上限配置：无法创建终结点配置：有效负载无效
* **ERR_ENDPOINTCONFIG_112**：上限配置：无法创建终结点配置：应为JSON负载
* **ERR_AUTHORING_ENDPOINTCONFIG_1**：无效的服务名称`<!--<given value>-->`：必须为“dataSource”或“action”

潜在的警告是：

**ERR_ENDPOINTCONFIG_106**：上限配置：未定义最大HTTP连接：默认情况下无限制

## 用例

在此部分中，您将找到五个主要用例，您可以执行这些用例来管理[!DNL Journey Orchestration]中的上限配置。

为帮助您进行测试和配置，可点击[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)获取 Postman 集合。

此“Postman 集合”已设置为通过 __[Adobe I/O 控制台的集成](https://console.adobe.io/integrations) > 试用 > 为 Postman 下载__&#x200B;共享 Postman 变量集合，它会使用选定的集成值生成 Postman 环境文件。

下载并上传到 Postman 后，您需要添加三个变量：`{JO_HOST}`、`{BASE_PATH}` 和 `{SANDBOX_NAME}`。
* `{JO_HOST}`：[!DNL Journey Orchestration]网关 URL
* `{BASE_PATH}`：API 的入口点。值为“/authoring”
* `{SANDBOX_NAME}`：标头 **x-sandbox-name**（例如，“prod”），对应将执行 API 操作的沙盒名称。有关更多信息，请参阅[沙盒概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hans)。

在以下部分中，您将找到用于执行用例的 Rest API 调用排序列表。

用例n°1： **创建和部署新上限配置**

1. list
1. create
1. candeploy
1. deploy

用例n°2： **更新和部署尚未部署上限配置**

1. list
1. get
1. update
1. candeploy
1. deploy

用例n°3： **取消部署并删除已部署的上限配置**

1. list
1. undeploy
1. delete

用例n°4： **删除已部署的上限配置。**

在仅一个 API 调用中，您可以使用 forceDelete 参数取消部署和删除配置。
1. list
1. 删除，使用 forceDelete 参数

用例n°5： **更新已部署的上限配置**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
