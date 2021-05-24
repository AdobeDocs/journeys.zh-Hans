---
product: adobe campaign
solution: Journey Orchestration
title: 与外部系统集成
description: 了解集成外部系统时的最佳实践
feature: 历程
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# 与外部系统集成{#external-systems}

本页介绍集成外部系统时Journey Orchestration提供的不同防护以及最佳实践：如何使用上限API优化对外部系统的保护，如何配置历程超时以及重试的工作方式。

Journey Orchestration允许您通过自定义数据源和自定义操作配置与外部系统的连接。 例如，这允许您使用来自外部预订系统的数据扩充您的历程，或使用第三方系统(如Epsilon或Facebook)发送消息。

在集成外部系统时，您可能会遇到一些问题，系统可能运行缓慢、可能停止响应，或者可能无法处理较大的卷。 Journey Orchestration提供了多个护栏，以防止系统过载。

所有外部系统在性能方面都各不相同。 您需要根据每个用例调整配置。

当Journey Orchestration执行对外部API的调用时，将按照以下方式执行技术防护：

1. 上限：应用上限规则
2. 超时并重试：

## 上限

内置上限API提供了上游技术护栏，可帮助保护外部系统。 您需要预先评估外部API的容量。 例如，如果Journey Orchestration每秒发送1000个调用，而您的系统每秒只能支持100个调用，则您需要定义上限规则，以便您的系统不会饱和。

在特定端点（称为的URL）的沙堆级别定义上限规则。 在运行时，Journey Orchestration会验证是否定义了上限规则，并在调用该端点期间应用定义的速率。 如果调用数超过定义的速率，则会丢弃剩余的调用。

上限规则特定于一个端点，但全局应用于沙盒的所有历程。 这意味着，调用插槽在沙盒的所有历程之间共享。 例如，假设您的外部系统已定义为每秒100个调用的上限，并且该上限会在10个不同历程中由自定义操作调用。 如果一个历程每秒收到200个呼叫，它将保持100个插槽可用，并丢弃剩余的100个插槽。 由于已超出最大速率，因此其他9个历程将没有任何可用插槽。 此粒度有助于保护外部系统免遭过载和崩溃。

由于上限限制而丢弃的调用在报表中会被计为错误。

要了解如何配置上限规则，请参阅[此页面](../api/timezone-management.md)。

## 超时和重试

Ensuite -> timeout defini， et qui definir le temps maximal qu&#39;on a lapple au sys externe. 吊坠的舞曲，关于苹果的主题。 在出现“fait un appel”时，s i&#39;apple dure moinre longtemps que le timeout ca marche， s i plus longtemps on voit ca comme une timeout error， et coté reporting compabilisé comme une erreur. 请重试“i&#39;apple echoue”(puner sur 500 ou autre)。 最多3次重试，可配置pas。 SI可以执行超时（第2段Essai，mais depasse le timeout）。 为了必要，可以。 超时在max qu&#39;on alloue a apple et aux retries是错误。

