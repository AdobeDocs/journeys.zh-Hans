---
title: 限制API说明
description: 进一步了解Capping API。
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ca4dc447d8ae4ee18e50d7e9a18faf3fa47ae223
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 1%

---


# 使用上限设置API

## 简介

[!DNL Journey Orchestration]s API支持5000事件/秒，但某些外部系统或API无法具有同等的吞吐量。 因此，我们附 [!DNL Journey Orchestration] 带一个名为Capping API的专用功能来监视和限制我们对外部系统的速率。

在数据源配置过程中，您将定义到系统的连接以检索将在您的旅程中使用的其他信息，或者为操作定义，您将配置第三方系统的连接以发送消息或API调用。 每次由旅程执行API调用时，将查询限制API，该调用将通过API引擎进行。 如果定义了限制，则会拒绝该调用，并且外部系统不会过载。

要了解有关操作或数据源配置的更多信息，请参 [阅关于操作](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html)[或关于数据源](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## 资源

>[!NOTE]
>
>此处 [!DNL Journey Orchestration] 提供的Swagger文件中对封顶API进行 [了说明](https://adobedocs.github.io/JourneyAPI/docs/)。

要将此API用 [!DNL Journey Orchestration] 于您的实例，您需要使用AdobeI/O控制台。 您可以通过以下方式进行开始 [：按照Adobe开发人员控制](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 台快速入门，然后使用本页中的各个部分。

要测试和准备集成，此处提供邮递员 [集合](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

## 身份验证

### 设置 API 访问

[!DNL Journey Orchestration] 通过以下步骤设置API访问。 Adobe I/O文档中详细介绍了 [每个步骤](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要在Adobe I/O中管理证书，请确保您对组织或 <b>管理控制台</b> 中的开发人员帐 [户拥有](https://helpx.adobe.com/enterprise/using/manage-developers.html) 系统管理员权限。

1. **检查您有数字证书**，或根据需要创建数字证书。 在以下步骤中需要随证书提供的公钥和私钥。
1. **在Adobe I/O中创建[!DNL Journey Orchestration]与** Service的新集成并进行配置。 需要产品用户档案访问，以 [!DNL Journey Orchestration] 及Adobe Experience Platform。 随后将生成您的凭据（API密钥、客户端机密……）。
1. **从先前生成的凭据创建JSON Web** Token(JWT)，然后使用您的私钥对其进行签名。 JWT会对Adobe验证您的身份并授予您对API的访问权限时所需的所有身份和安全信息进行编码。 此步骤详见本 [节](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **通过POST请求或通过开发人员** 控制台界面将您的JWT交换为访问令牌。 此访问令牌必须用于API请求的每个头中。

要建立安全的服务到服务Adobe I/O API会话，对Adobe服务的每个请求都必须在“授权”标题中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;组织>**: 这是您的个人组织ID,Adobe为每个实例提供一个组织ID:

   * &lt;组织>: 您的生产实例
   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 创建新集成时，您还可以在许可证列表(请参阅Adobe I/O文 <a href="https://www.adobe.io/authentication.html">档)中将其检索到Adobe</a>I/O。

* **&lt;ACCESS_TOKEN>**: 您的个人访问令牌，通过POST请求交换JWT时检索到。

* **&lt;API_KEY>**: 您的个人API密钥。 它在创建与服务的新集成后在Adobe I/O中提 [!DNL Journey Orchestration] 供。



## 限制API说明

上限设置API可帮助您创建、配置和监控您的上限设置配置。

| 方法 | 路径 | 说明 |
|---|---|---|
| [!DNL POST] | 列表/endpointConfigs | 获取端点封顶配置的列表 |
| [!DNL POST] | /endpointConfigs | 创建端点封顶配置 |
| [!DNL POST] | /endpointConfigs/{uid}/deploy | 部署端点封顶配置 |
| [!DNL POST] | /endpointConfigs/{uid}/undeploy | 取消部署端点上限设置配置 |
| [!DNL POST] | /endpointConfigs/{uid}/canDeploy | 检查是否可以部署终结点上限设置配置 |
| [!DNL PUT] | /endpointConfigs/{uid} | 更新端点封顶配置 |
| [!DNL GET] | /endpointConfigs/{uid} | 检索端点封闭配置 |
| [!DNL DELETE] | /endpointConfigs/{uid} | 删除入点上限设置配置 |

创建或更新配置时，将自动执行检查以确保有效负荷的语法和完整性。
如果出现问题，操作会返回警告或错误以帮助您更正配置。



## 端点配置

下面是端点配置的基本结构：

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

### 例如：

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

调用 **canDeploy** 方法时，该进程验证配置并返回由其唯一ID标识的验证状态，其中一种为：

```
"ok" or "error"
```

潜在错误有：

* **ERR_ENDPOINTCONFIG_100**: 上限配置： 缺少或无效url
* **ERR_ENDPOINTCONFIG_101**: 上限配置： 格式错误的url
* **ERR_ENDPOINTCONFIG_102**: 上限配置： 格式错误的url: host:port中不允许url中的通配符
* **ERR_ENDPOINTCONFIG_103**: 上限配置： 缺少HTTP方法
* **ERR_ENDPOINTCONFIG_104**: 上限配置： 未定义呼叫等级
* **ERR_ENDPOINTCONFIG_107**: 上限配置： 最大调用计数无效(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: 上限配置： 最大调用计数无效(periodInMs)
* **ERR_ENDPOINTCONFIG_111**: 上限配置： 无法创建终结点配置： 有效负荷
* **ERR_ENDPOINTCONFIG_112**: 上限配置： 无法创建终结点配置： 需要JSON有效负荷
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: 服务名无效 <!--<given value>-->: 必须为“dataSource”或“action”


潜在的警告是：

**ERR_ENDPOINTCONFIG_106**: 上限配置： 未定义最大HTTP连接数： 默认情况下无限制



## 用例

在本节中，您将找到管理中的上限设置配置时可执行的五个主要用例 [!DNL Journey Orchestration]。

为了帮助您进行测试和配置，此处提供了Postman [集合](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

此邮递员集合已设置为共享通过 __[Adobe I/O控制台的“集成”](https://console.adobe.io/integrations)__>“试用”>“下载邮递员”生成的邮递员变量集合，该集合生成具有选定集成值的邮递员环境文件。

下载并上传到Postman后，您需要添加三个变量： `{JO_HOST}`,`{Base_Path}` and `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] 网关URL
* `{BASE_PATH}` : 入口点。 值为“/authoring”
* `{SANDBOX_NAME}` : 与执 **行API操作的沙箱名** （例如，“prod”）对应的标题x-sandbox-name。 有关更多 [信息，请参](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) 阅沙箱概述。

在以下部分中，您将找到Rest API调用的有序列表以执行用例。

用例n°1: **创建和部署新的上限配置**

1. 列表
1. create
1. candeploy
1. 部署

用例n°2: **更新和部署尚未部署的上限设置配置**

1. 列表
1. 获取
1. 更新
1. candeploy
1. 部署

用例n°3: **取消部署和删除已部署的上限设置配置**

1. 列表
1. 取消部署
1. 删除

用例n°4: **删除已部署的上限设置配置。**

在仅一个API调用中，可以使用forceDelete参数取消部署和删除配置。
1. 列表
1. 删除，使用forceDelete参数

用例n°5: **更新已部署的上限设置配置**

1. 列表
1. 获取
1. 更新
1. 取消部署
1. candeploy
1. 部署

