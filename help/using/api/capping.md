---
product: adobe campaign
title: API描述上限
description: 进一步了解上限API。
products: journeys
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: e42ef98b1d84d8311cf49967ec75ec9be6cc53f1
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 1%

---

# 使用上限API

## 简介

[!DNL Journey Orchestration]的API支持5000事件/秒，但某些外部系统或API的吞吐量无法相等。因此，[!DNL Journey Orchestration]提供了称为上限API的专用功能，用于监控和限制我们对外部系统的速率。

在数据源配置期间，您将定义与系统的连接，以检索将在您的历程中使用的其他信息，或者对于操作定义，您将配置第三方系统的连接以发送消息或API调用。 每次由历程执行API调用时，即会查询上限API，调用都会通过API引擎。 如果定义了限制，则调用将被拒绝，外部系统将不会过载。

对于外部数据源，每秒的最大调用数设置为15。 如果呼叫数超过每秒15次，则会丢弃剩余的呼叫。 您可以提高专用外部数据源的此限制。 联系Adobe以将端点列入白名单。 对于公共外部数据源，这是不可能的。 要详细了解集成外部系统时的最佳实践和防护，请参阅此[页面](../about/external-systems.md)。

要了解有关操作或数据源配置的更多信息，请参阅[关于操作](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html)或[关于数据源](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## 资源

>[!NOTE]
>
>[!DNL Journey Orchestration]上限API在[此处](https://adobedocs.github.io/JourneyAPI/docs/)提供的Swagger文件中进行了描述。

要将此API与[!DNL Journey Orchestration]实例一起使用，您需要使用AdobeI/O控制台。 您可以按照以下步骤开始操作：[Adobe开发人员控制台快速入门](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) ，然后使用本页中的部分。

要测试和准备集成，[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)提供了Postman集合。

## 身份验证

### 设置 API 访问

[!DNL Journey Orchestration] 通过以下步骤设置API访问。[Adobe I/O文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中详细描述了每个步骤。

>[!CAUTION]
>
>要在Adobe I/O中管理证书，请确保您拥有组织的<b>系统管理员</b>权限，或在Admin Console中拥有[开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html)权限。

1. **检查您是否拥有数字证书**，或根据需要创建一个证书。在以下步骤中需要随证书一起提供的公钥和私钥。
1. **在Adobe I/O中创建与服务 [!DNL Journey Orchestration]** 的新集成并对其进行配置。[!DNL Journey Orchestration]和Adobe Experience Platform需要产品配置文件访问权限。 随后将生成您的凭据（API密钥、客户端密钥……）。
1. **从之前生成的凭据创建JSON Web令牌(JWT)** ，然后使用您的私钥对其进行签名。JWT会对Adobe验证您的身份并授予您访问API的权限所需的所有身份和安全信息进行编码。 此[部分](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)中详细介绍了此步骤
1. **通过POST请求或** 通过开发人员控制台界面交换JWT以进行访问令牌。此访问令牌必须用在API请求的每个标头中。

要建立安全的服务到服务Adobe I/OAPI会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:这是您的个人组织ID，Adobe会为您的每个实例提供一个组织ID:

   * &lt;organization> :您的生产实例

   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 创建新集成时，您还可以在许可证列表中将其检索到Adobe I/O中(请参阅<a href="https://www.adobe.io/authentication.html">Adobe I/O文档</a>)。

* **&lt;access_token>**:您的个人访问令牌，在通过POST请求交换JWT时检索。

* **&lt;api_key>**:您的个人API密钥。在创建[!DNL Journey Orchestration]服务的新集成后，该集成在Adobe I/O中提供。



## API描述上限

上限API可帮助您创建、配置和监控上限配置。

| 方法 | 路径 | 说明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | 获取端点上限配置的列表 |
| [!DNL POST] | /endpointConfigs | 创建端点上限配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 部署端点上限配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | 取消部署端点上限配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 检查是否可以部署端点上限配置 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 更新端点上限配置 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 检索端点上限配置 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 删除入点上限配置 |

创建或更新配置后，将自动执行检查以保证有效负载的语法和完整性。
如果出现某些问题，操作会返回警告或错误，以帮助您更正配置。



## 端点配置

以下是端点配置的基本结构：

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

### 示例:

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


## 警告和错误

当调用&#x200B;**canDeploy**&#x200B;方法时，该过程将验证配置并返回由其唯一ID标识的验证状态，其中任一ID:

```
"ok" or "error"
```

潜在错误包括：

* **ERR_ENDPOINTCONFIG_100**:上限配置：缺少或无效的url
* **ERR_ENDPOINTCONFIG_101**:上限配置：格式错误的url
* **ERR_ENDPOINTCONFIG_102**:上限配置：url格式错误：host:port中不允许在url中使用通配符
* **ERR_ENDPOINTCONFIG_103**:上限配置：缺少HTTP方法
* **ERR_ENDPOINTCONFIG_104**:上限配置：未定义呼叫评级
* **ERR_ENDPOINTCONFIG_107**:上限配置：最大调用计数无效(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:上限配置：最大调用计数无效(periodInMs)
* **ERR_ENDPOINTCONFIG_111**:上限配置：无法创建端点配置：无效负载
* **ERR_ENDPOINTCONFIG_112**:上限配置：无法创建端点配置：应为JSON有效负载
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:无效的服务名称 `<!--<given value>-->`:必须是“dataSource”或“action”


潜在的警告是：

**ERR_ENDPOINTCONFIG_106**:上限配置：未定义的最大HTTP连接数：默认情况下不限制



## 用例

在此部分中，您将找到可用于管理[!DNL Journey Orchestration]中的上限配置的五个主要用例。

为帮助您进行测试和配置，[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)提供了Postman集合。

此Postman集合已设置为共享通过&#x200B;__[Adobe I/O控制台的集成](https://console.adobe.io/integrations) >尝试>下载Postman__&#x200B;生成的Postman变量集合，该集合会生成一个包含选定集成值的Postman环境文件。

下载并上传到Postman后，您需要添加三个变量：`{JO_HOST}`、`{Base_Path}`和`{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration] 网关URL
* `{BASE_PATH}` :API的入口点。值为“/authoring”
* `{SANDBOX_NAME}` :与将 **在其中执行API操作的沙盒名称对应的标头x-sandbox-name** （例如“prod”）。有关更多信息，请参阅[沙箱概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 。

在以下部分中，您将找到用于执行用例的Rest API调用排序列表。

用例n°1:**创建和部署新的上限配置**

1. 列表
1. 创建
1. candeploy
1. 部署

用例n°2:**更新和部署尚未部署的上限配置**

1. 列表
1. get
1. 更新
1. candeploy
1. 部署

用例n°3:**取消部署和删除已部署的上限配置**

1. 列表
1. 取消部署
1. 删除

用例n°4:**删除已部署的上限配置。**

在仅一个API调用中，您可以使用forceDelete参数取消部署和删除配置。
1. 列表
1. 删除，使用forceDelete参数

用例n°5:**更新已部署的上限配置**

1. 列表
1. get
1. 更新
1. 取消部署
1. candeploy
1. 部署
