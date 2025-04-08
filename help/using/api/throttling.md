---
product: adobe campaign
title: 使用 API 限制
description: 进一步了解“API 限制”
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 91%

---

# 使用 API 限制


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


节流API可帮助您创建、配置和监视节流配置，以限制每秒发送的事件数。

>[!IMPORTANT]
>
>目前，仅允许为每个组织使用一个配置。必须在生产沙盒上定义配置（通过标头中的 x-sandbox-name 提供）。
>
>配置会在组织级别应用。
>
>当达到 API 中设置的限制时，后续事件将排队等待 6 小时。无法修改此值。

## API 限制说明 {#description}

| 方法 | 路径 | 描述 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | 获取限制配置列表 |
| [!DNL POST] | /throttlingConfigs | 创建限制配置 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | 部署限制配置 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | 取消部署限制配置 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | 检查是否可以部署限制配置 |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | 更新限制配置 |
| [!DNL GET] | /throttlingConfigs/`{uid}` | 检索限制配置 |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | 删除限制配置 |

## 限制配置{#configuration}

以下是限制配置的结构。**name** 和 **description** 属性是可选项。

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

示例：

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## 错误

创建或更新配置时，该流程会验证给定配置并返回由其“唯一 ID”标识的验证状态，这可以是：

```
"ok" or "error"
```

>[!IMPORTANT]
>
>属性 **maxThroughput**、**urlPattern** 和 **methods** 是必填项。
>
>**maxThroughput** 的值必须在 200-5000 范围内。

创建、删除或部署限制配置时，可能会出现以下错误：

* **ERR_THROTTLING_CONFIG_100**：限制配置：`<mandatory attribute>`必需
* **ERR_THROTTLING_CONFIG_101**：限制配置：maxThroughput 是必填项，且必须大于或等于 200 且小于或等于 5000
* **ERR_THROTTLING_CONFIG_104**：限制配置：格式错误的 URL 模式
* **ERR_THROTTLING_CONFIG_105**：限制配置：URL 模式的主机部分不允许使用通配符
* **ERR_THROTTLING_CONFIG_106**：限制配置：无效负载
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**，“无法删除已部署的限制配置。请在删除之前取消部署”
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**，“无法删除限制配置：发生意外错误”
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**，“无法部署限制配置：发生意外错误”
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**，“无法取消部署限制配置：发生意外错误”
* **THROTTLING_CONFIG_GET_ERROR: 1460**，“无法获取限制配置：发生意外错误”
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**，“无法更新限制配置：运行时版本处于不活动状态”
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**，“无法更新限制配置：发生意外错误”
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**，“禁止对限制配置执行操作：非生产沙盒”
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**，“无法创建限制配置：发生意外错误”
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**，“无法创建限制配置：仅允许为每个组织使用一个配置”
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**，“无法部署限制配置：已部署”
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**，“找不到限制配置”
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**，“无法取消部署限制配置：尚未部署”

**错误示例**

尝试在非生产沙盒上创建配置时：

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

如果给定的沙盒不存在：

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

尝试创建其他配置时：

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## 用例 {#uc}

为帮助您进行测试和配置，可点击[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json)获取 Postman 集合。

此“Postman 集合”已设置为通过 __[Adobe I/O 控制台的集成](https://console.adobe.io/integrations) > 试用 > 为 Postman 下载__&#x200B;共享 Postman 变量集合，它会使用选定的集成值生成 Postman 环境文件。

下载并上传到 Postman 后，您需要添加三个变量：`{JO_HOST}`、`{BASE_PATH}` 和 `{SANDBOX_NAME}`。
* `{JO_HOST}`：[!DNL Journey Orchestration]网关 URL
* `{BASE_PATH}`：API 的入口点。值为“/authoring”
* `{SANDBOX_NAME}`：标头 **x-sandbox-name**（例如，“prod”），对应将执行 API 操作的沙盒名称。有关更多信息，请参阅[沙盒概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hans)。

在以下部分中，您将找到用于执行用例的 Rest API 调用排序列表。

用例 1：**创建和部署新的限制配置**

1. list
1. create
1. candeploy
1. deploy

用例 2：**更新并部署尚未部署的限制配置**

1. list
1. get
1. update
1. candeploy
1. deploy

用例 3：**取消部署和删除已部署的限制配置**

1. list
1. undeploy
1. delete

用例 4：**删除已部署的限制配置**

在仅一个 API 调用中，您可以使用 forceDelete 参数取消部署和删除配置。

1. list
1. 删除，使用 forceDelete 参数

用例 5：**更新已部署的限制配置**

>[!NOTE]
>
>在更新之前，无需取消部署配置

1. list
1. get
1. update

## 运行时级别的配置生命周期 {#config}

取消部署配置后，该配置在运行时级别被标记为不活动，并且在 24 小时内将继续处理待处理事件。然后，会在运行时服务中删除它。

取消部署配置后，可以更新和重新部署配置。这将创建新的运行时配置，在即将执行的操作中将使用该配置。

更新已部署的配置时，会立即使用新值。底层系统资源将自动调整。与取消部署然后重新部署配置相比，这是最佳选择。

## 响应示例 {#responses}

**创建 - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**更新 - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**读取（更新后）- GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**读取（部署后）- GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
