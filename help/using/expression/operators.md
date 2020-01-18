---
title: 运营商
description: 了解高级表达式中的运算符
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---



# 运营商 {#concept_wd5_pj5_dgb}

操作符有两种：一元运算符和二进制运算符。 有左一元运算符和右一元运算符。

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

以下是支持的运算符列表：

## 逻辑

<table>
<thead>
<tr ><th  >运算符</th><th  >文本表达式</th><th  >示例</th></tr>
</thead>
<tbody>
<tr >&gt;<td>和</td><td><p><pre>&lt;expression1&gt;和&lt;expression2&gt;</pre></p>&lt;expression1&gt;和&lt;expression2&gt;都必须是布尔型。 结果是布尔值。</td><td><pre>3.14 &gt; 2和3.15 &lt; 1</pre></td></tr>
<tr ><td>或</td><td><p><pre>&lt;expression1&gt;或&lt;expression2&gt;</pre></p><p>&lt;expression1&gt;和&lt;expression2&gt;都必须是布尔型。</p><p> 结果是布尔值。</p></td><td><p><pre>3.14 &gt; 2或3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;expression&gt;</pre></p><p>&lt;expression&gt;必须是布尔型。</p><p> 结果是布尔值。</p></td><td><pre>不是3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## 比较

<table>
<thead>
<tr ><th  >运算符</th><th  >文本表达式 </th><th  >示例</th></tr>
</thead>
<tbody><tr ><td>为null</td><td><p><pre>&lt;expression&gt;为null</pre></p><p>结果是布尔值。</p><p>请注意，null表示表达式没有计算值。</p></td><td><pre>@{BarBeacon.location}为空</pre></td></tr>
<tr ><td>不是null</td><td><p><pre>&lt;expression&gt;不为null</pre></p><p>结果是布尔值。</p><p>请注意，null表示表达式没有计算值。</p></td><td><pre>@不为空</pre></td></tr>
<tr ><td>具有null</td><td><p><pre>&lt;expression&gt;为null</pre>&lt;expression&gt;必须是列表。</p><p>结果是布尔值。</p><p>用于标识列表是否至少包含一个null值。</p></td><td><p><pre>["foo", "bar", null]为null</pre></p>返回true<p><pre>["foo", "bar", ""]有null</pre></p> 返回false，因为“”不被视为null。</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>&lt;expression1&gt;和&lt;expression2&gt;必须具有相同的数据类型。</p><p> 结果是布尔值。</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> &lt;expression1&gt;和&lt;expression2&gt;必须具有相同的数据类型。</p><p> 结果是布尔值。</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>可以将日期时间与日期时间进行比较。</p><p>只能将Datetime与Datetimeonly进行比较。</p><p>整数或小数都可以与整数或小数进行比较。</p><p>任何其他组合都是禁止的。</p><p>结果是布尔值。</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>可以将日期时间与日期时间进行比较。</p><p>只能将Datetime与Datetimeonly进行比较。</p><p>整数或小数都可以与整数或小数进行比较。</p><p>任何其他组合都是禁止的。</p><p>结果是布尔值。</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>可以将日期时间与日期时间进行比较。</p><p>只能将Datetime与Datetimeonly进行比较。</p><p>整数或小数都可以与整数或小数进行比较。</p><p>任何其他组合都是禁止的。</p><p>结果是布尔值。</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>可以将日期时间与日期时间进行比较。</p><p>只能将Datetime与Datetimeonly进行比较。</p><p>整数或小数都可以与整数或小数进行比较。</p><p>任何其他组合都是禁止的。</p><p>结果是布尔值。</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## 算术

<table>
<thead>
<tr ><th  >运算符</th><th>文本表达式 </th><th  >示例</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>这两个表达式都必须是数字（整数或小数）。 </p><p>结果也是数字。</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>退货3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> 这两个表达式都必须是数字（整数或小数）。</p><p> 结果也是数字。</p></td><td><p><pre>2 - 1</pre></p>退货1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>这两个表达式都必须是数字（整数或小数）。 </p><p>结果也是数字。</p><p>&lt;expression2&gt;不能等于0（返回0）。</p></td><td><p><pre>4 / 2</pre></p>退货2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> 这两个表达式都必须是数字（整数或小数）。 </p><p>结果也是数字。</p></td><td><p><pre>3 * 4</pre></p>退货12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>这两个表达式都必须是数字（整数或小数）。</p><p> 结果也是数字。</p></td><td><p><pre>3 % 2</pre></p>返回1。</td></tr>
</tbody>
</table>

## 数学

<table>
<thead>
<tr ><th  >运算符</th><th  >文本表达式 </th><th  >示例</th></tr>
</thead>
<tbody><tr ><td>数字</td><td><p><pre>&lt;expression&gt;是数字</pre></p><p>表达式的类型是整数或小数。</p></td><td><pre>@是数字</pre></td></tr>
<tr ><td>integer</td><td><p><pre>&lt;expression&gt;是整数</pre></p><p>表达式的类型是整数。</p></td><td><pre>@是整数</pre></td></tr>
<tr ><td>小数</td><td><p><pre>&lt;expression&gt;是十进制的</pre></p><p>表达式的类型是十进制的。</p></td><td><pre>@是小数</pre></td></tr>

## 字符串

<table>
<thead>
<tr ><th  >运算符</th><th  >文本表达式 </th><th  >示例</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;string&gt; + &lt;expression&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;string&gt;</pre></p><p>它连接两个表达式。 </p><p>一个表达式必须是链式字符串。</p></td><td><p><pre>"当前时间是" +(now())</pre></p> 返回“当前时间为2019-09-23T09:30:06.693Z”<p><pre>(now())+ "是当前时间"</pre></p>返回“2019-09-23T09:30:06.693Z是当前时间”<p><pre>"a" + "b" + "c" + 1234</pre></p> 返回“abc1234”。</td></tr>
</tbody>
</table>

## 日期

<table>
<thead>
<tr ><th  >运算符</th><th  >文本表达式 </th><th  >示例</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;expression + &lt;duration&gt;</pre></p><p>在dateTime、dateTimeOnly或duration后面附加持续时间。</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>返回2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>返回2011-12-03T15:30:30<p><pre>now()+ toDuration("PT1H")</pre></p><p>从当前时间起1小时后返回dateTime（带有UTC时区）</p><p><pre>toDuration("PT1H")+ toDuration("PT1H")</pre></p><p>返回PT2H</p></td></tr>
</tbody>
</table>