---
product: adobe campaign
title: journeyStep 事件操作执行字段
description: journeyStep 事件操作执行字段
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 12%

---

# journeyStep 事件操作执行字段 {#sharing-execution-fields}

此mixin將由journeyStepEvent和journeyStepProfileEvent共用。

如果步驟有要處理的動作，這些欄位將會新增至事件裝載。

## actionID

正在執行的動作ID。

类型：字符串

## actionName

動作的名稱。 如果尚未設定名稱，則會採用stepName。

类型：字符串

## actionType

動作的型別。

类型：字符串

## actionParameterized

指出動作是否已引數化。

类型：布尔值

## actionExecutionTime

執行目前動作所需的時間（毫秒）。

型別： long

## actionExecutionError

呼叫動作時發生的錯誤型別。

类型：字符串

值：
* http
* 上限
* timeout
* error

## actionExecutionErrorCode

動作執行錯誤的程式碼。 如果錯誤有程式碼（例如HTTP程式碼），則會出現。

类型：字符串

## actionExecutionOriginError

在以下兩種情況下，可能會發生逾時：

* 在第一次嘗試時會執行動作。 在此情況下，執行尚未完成，因此沒有基礎錯誤
* 重試：在此情況下，actionExecOrigError/actionExecOrigErrorCode會說明在重試之前嘗試遇到的錯誤。

例如，會傳送電子郵件，而第一次嘗試時會傳回HTTP 500錯誤。 會重試擷取，但2次嘗試的持續時間超過逾時。 然後該動作執行會標籤為逾時。 動作部分看起來會像這樣：

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

类型：字符串

## actionExecutionOriginCode

actionExecOrigError的錯誤碼。

类型：字符串

## actionBusinessType

指示動作的型別。

值：

* 內建
* ACS電子郵件
* ACS簡訊
* ACS推播
* 客戶
* Epsilon
* ...

类型：字符串

## deliveryJobID

這描述了批次歷程的傳遞工作ID。

类型：字符串

## batchdeliveriyid

這描述了批次歷程的傳遞ID。

类型：字符串

## fromSegmentTrigger

這描述了批次歷程是否從受眾區段觸發。

类型：布尔值

## actionSchedulerCount

在步驟處理期間傳送至排程器服務的排程器通知要求計數。

型別： long
