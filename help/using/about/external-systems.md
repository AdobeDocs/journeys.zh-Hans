---
product: adobe campaign
solution: Journey Orchestration
title: 与外部系统集成
description: 了解集成外部系统时的最佳实践
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 5%

---

# 与外部系统集成 {#external-systems}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_



本页介绍Journey Orchestration在集成外部系统时提供的各种护栏以及最佳实践：如何使用上限API优化外部系统的保护、如何配置历程超时以及重试的工作方式。

Journey Orchestration允许您通过自定义数据源和自定义操作配置与外部系统的连接。 例如，您可以使用来自外部预订系统的数据扩充您的历程，或使用第三方系统（如Epsilon或Facebook）发送消息。

在集成外部系统时，可能会遇到几个问题：系统可能变慢、停止响应，或者可能无法处理较大的卷。 Journey Orchestration提供了多个护栏以保护您的系统免受过载。

所有外部系统在性能方面均不同。 您需要根据用例调整配置。

当Journey Orchestration执行对外部API的调用时，技术护栏将按如下方式执行：

1. 应用上限规则：如果达到最大速率，将丢弃剩余调用。

2. 超时并重试：如果达到了上限规则，Journey Orchestration将尝试执行调用，直到到达超时持续时间结束为止。

## 上限{#capping}

内置的Capping API提供有助于保护外部系统的上游技术护栏。

对于外部数据源，每秒的最大调用数设置为15。 如果呼叫数超过每秒15次，则会丢弃剩余的呼叫。 您可以提高专用外部数据源的此限制。 联系Adobe以将端点包含在允许列表中。 对于公共外部数据源，这是不可能的。

对于自定义操作，您需要评估外部API的容量。 例如，如果Journey Optimizer每秒发送1000次调用，而您的系统仅支持每秒100次调用，则需要定义上限规则，以便您的系统不会饱和。

为特定端点（调用的URL）在沙盒级别定义上限规则。 在运行时，Journey Orchestration验证是否定义了上限规则，并在调用该端点期间应用定义的速率。 如果呼叫数超过定义的速率，则会丢弃剩余的呼叫，并在报表中计为错误。

上限规则特定于一个端点，但全局适用于沙盒的所有历程。 这意味着沙盒的所有历程之间共享上限插槽。

例如，假设您为外部系统定义了每秒100次调用的上限规则。 在 10 个不同历程中，系统由自定义操作调用。如果一个历程每秒接收200次调用，它将使用可用的100个插槽并放弃剩余的100个插槽。 由于超出了最大使用率，因此其他 9 个历程将没有任何位置。此粒度有助于避免使外部系统出现过载和崩溃。

要了解有关API上限以及如何配置上限规则的更多信息，请参阅[此页面](../api/capping.md)。

## 超时和重试{#timeout}

如果满足上限规则，则应用超时规则。

在每个历程中，您可以定义超时持续时间。 这允许您在调用外部系统时设置最大持续时间。 超时持续时间在历程的属性中配置。 请参见[此页面](../building-journeys/changing-properties.md#timeout_and_error)。

此超时对于所有外部调用（自定义操作和自定义数据源中的外部API调用）都是全局的。 默认情况下，设置为5秒。

在定义的超时持续时间内，Journey Orchestration会尝试调用外部系统。 在第一次调用后，最多可以执行三次重试，直到达到超时持续时间结束为止。 无法更改重试次数。

每次重试使用一个插槽。 如果您的限制为每秒100次调用，并且每个调用需要重试两次，则速率降至每秒30次调用（每个调用使用3个插槽：第一次调用和两次重试）。

超时持续时间值取决于用例。 如果您希望快速发送消息（例如，在客户端进入商店时），则您不希望设置较长的超时。 此外，超时时间越长，放入队列中的项目就越多。 这会极大地影响性能。 如果Journey Orchestration每秒执行1000次调用，则保留5秒或15秒的数据会迅速让系统不堪重负。

我们以5秒的超时为例。

* 第一个调用持续少于5秒：调用成功，不执行重试。
* 第一个调用持续的时间更长5秒：调用被取消并且不会重试。 在报表中将被计为超时错误。
* 第一次调用在2秒后失败（外部系统返回错误）：如果存在上限插槽，则重试时间还剩3秒。
   * 如果在5秒结束前三次重试均成功，则会执行调用，且不会出现任何错误。
   * 如果在重试期间到达超时时长的结尾，则调用会被取消，并在报表中计为超时错误。

## 常见问题解答{#faq}

**如何配置上限规则？ 是否存在默认上限规则？**

默认情况下，没有上限规则。 使用上限API，在特定端点（调用的URL）的沙盒级别定义上限规则。 请参阅[此部分](../about/external-systems.md#capping)和[此页面](../api/capping.md)。

**执行多少次重试？ 我可以更改重试次数或定义重试之间的最短等待时间吗？**

对于给定的调用，在第一次调用后最多可以执行三次重试，直到达到超时持续时间结束为止。 无法更改重试次数和每次重试之间的时间。 请参阅[此小节](../about/external-systems.md#timeout)。

**我可以在何处配置超时？ 是否存在最大值？**

在每个历程中，您可以定义超时持续时间。 超时持续时间在历程的属性中配置。 超时持续时间必须介于1秒和30秒之间。 请参阅[此部分](../about/external-systems.md#timeout)和[此页面](../building-journeys/changing-properties.md#timeout_and_error)。
