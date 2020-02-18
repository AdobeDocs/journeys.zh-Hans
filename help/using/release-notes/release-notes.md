---
title: 发行说明
description: 了解发行说明
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# 发行说明 {#release-notes}

本页列出了旅程安排的所有新增功能和改进。
您还可以查阅文档 [更新](../release-notes/documentation-updates.md)。

## 第1季度版本- 2019年2月 {#q1-release---february-2019}

**时区管理**

现在可在旅程级别管理时区。 在旅程属性中添加了两个参数：

* “ **时区** ”(Timezone)下拉列表允许您选择特定时区。 默认情况下，使用浏览器的时区。

* 配置 **文件时区** （如果可用）复选框允许您使用进入旅程的人员的Experience Platform配置文件时区。 否则，将使用下拉列表中定义的时区。 此功能与不带命名空间的journeys不兼容。

**上下文帮助**

现在，跨不同的旅程编排屏幕提供了上下文帮助功能。 这意味着，只需单击一下，即可直接访问有关您当前使用的功能的文档。

要显示上下文帮助，请单击屏幕右上角的“i”图标。

目前，此功能在“主页”、“数据源”、“事件”和“操作”列表屏幕中可用。

**其他更改**

* 在测试模式下，新参数允许您定义更精细的时间。  等待时间活动可以持续。 这样，您就可以快速访问测试结果。

* 在测试模式下，您现在可以触发旅程中的所有事件。


* 新参数允许您定义时间。  等待时间活动可以持续。 这样，您就可以快速访问测试结果。

* Journeys Orchestration现已在EMEA推出。

* 调色板中的新图标，用于显示或不可用项目。 sans namespace. par default.

* 画布、解集、小图标、小编辑断开节点。

* 短切C列

* 调色板UI,icone de search results

* Pouvoir capper les调用des APIS externes（数据源或操作）。 marque n&#39;accepte 500 calls par seconde, elle pourra mettre un canding a 500 calls seconds qui evite de surchager system de loyalty tiers

* 测试日志。 Avantstatus = error. 在阿巴拉契亚山脉上。 Possibilityé de voir code reur phrase qu&#39;à renvoyé le system. -> ds un test en cas d&#39;erreur, systeme tiers，错误代码，错误响应。

* 停止删除旅程

* 旅程：版本1，满足最新要求

火星一号。


## GA版本- 2019年12月 {#ga-release---december-2019}

旅程编排现已正式推出。

利用存储在事件或数据源中的情境数据构建实时安排使用案例。

旅程安排允许实时安排由来自活动的情境式数据、Adobe Experience platform的信息或来自第三方API服务的数据提供支持。 应用程序根据客户的档案和行为确定在称为旅程的多步骤流中特定于客户的下一个最佳操作。 这包括最佳时间以及操作类型，如通过Adobe Campaign Standard交易消息传递功能（需要Adobe Campaign Standard）向消费者发送推送通知或第三方系统通知。 这些决定基于规则和Sensei得分。

[了解有关旅程编排的更多信息](../action/working-with-adobe-campaign.md) 。

其他资源：

* [教程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社区](https://www.adobe.com/go/journeyorchestrationcommunity)