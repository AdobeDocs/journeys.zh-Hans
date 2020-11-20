---
product: adobe campaign
solution: Journey Orchestration
title: 数据类型
description: 了解高级表达式中的数据类型
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---


# 数据类型 {#concept_gp3_rj5_dgb}

从技术上讲，常数始终包含数据类型。 在文本表达式中，我们只指定值。 数据类型可从值（例如字符串、整数、小数等）推断出来。 对于日期时间等特定情况，我们使用专门的函数来表示。

以下是数据类型表达式的表示方式：

<table>
    <thead>
        <tr>
        <td>数据类型</td>
        <td>说明</td>
        <td>文本表示</td>
        <td>示例</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>字符串</td>
        <td><p>常用字符序列。</p><p>除了来自环境的隐式大小（如可用内存量）之外，它没有任何特定大小。</p><p>JSON格式：字符串</p><p>序列化格式：UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>“&lt;value&gt;”</p></td>
        <td><p><pre>“hello world”</pre></p><p><pre>“hello world”</pre></p></td>
    </tr>
    <tr>
        <td>整数</td>
        <td><p>从-2^63到2^63-1的整数值。</p><p>JSON格式：数字</p></td>
        <td>&lt;整数值&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>小数</td>
        <td><p>小数。</p><p>它表示浮动值：</p>
        <p>-多次类型的最大正有限值，(2-2^-52)x2^1023</p>
        <p> -多次类型的最小正常值，2-1022</p>
        <p> -类型多次的最小正非零值，2 p-1074</p><p>JSON格式：数字</p><p>序列化格式：使用“.” 作为小数分隔符。</p></td>
        <td>&lt;integer value&gt;。&lt;整数值&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>布尔</td>
        <td><p>布尔值写小写：true或false</p><p>JSON格式：布尔值</p></td>
        <td><p>真</p><p>假</p></td>
        <td><p><pre>真</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>表示没有时区的日期时间，视为年月日时（分钟）（毫秒）。</p><p>它不存储或表示时区。</p><p>相反，它是日期的描述，与墙上钟显示的当地时间相结合。</p><p>如果没有其他信息（如偏移或时区），它不能表示时间线上的即时。</p><p>序列化格式：ISO-8601扩展的偏移日期时间格式。</p><p>它使用DateTimeFormatter。</p><p>ISO_LOCAL_DATE_TIME，用于反序列化和序列化值。</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">了解详情</a>。</td>
        <td><p>toDateTimeOnly（"&lt;ISO-8601格式中的dateTimeOnly&gt;"）</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>日期时间常数，也考虑时区。</p><p>它表示一个距UTC有偏移的日期时间。 它可以即时查看，并附加偏移信息。 </p><p>是在世界某个地方代表一个特定"时刻"的一种方式。</p><p>JSON格式：字符串。</p><p> 它必须封装在toDateTime函数中。</p><p>
        序列化格式：ISO-8601扩展的偏移日期时间格式。</p><p> 它使用DateTimeFormatter.ISO_OFFSET_DATE_TIME反序列化和序列化值。</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">了解详情</a>。 
        <p>您还可以传递一个传递新纪元值的整数。</p> <a href="https://www.epochconverter.com/">阅读更多</a>。</p>
        <p>时区可以由偏移或时区代码指定(例如：欧洲／巴黎，Z —— 表示UTC)。</p></td>
        <td><p>toDateTime（"&lt;ISO-8601格式中的dateTime&gt;"）</p>
        <p>toDateTime（&lt;以毫秒为单位的纪元的整数值&gt;）</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>(“2011-12-03T15:15:30Z”)</pre></p><p><pre>toDateTime</pre></p><p><pre>(“2011-12-03T15:15:30.123Z”)</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>(“2011-12-03T15:15:30.123-00:20”)</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>持续时间</td>
        <td><p>它表示基于时间的时间量，如“34.5秒”。</p><p> 它以毫秒为单位来建模数量或时间。</p><p>支持的时间单元有：毫秒、秒、分钟、小时、天，其中一天等于24小时。</p><p> 年份和月份不受支持，因为它们不是固定的时间。</p><p>JSON格式：字符串。 它必须封装在toDuration函数中。</p><p>序列化格式：要反序列化时区ID，它使用java函数java.time。</p><p>Duration.parse:接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，其天数被认为正好24小时。</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">了解详情</a>。</td>
        <td><p>toDuration（"&lt;ISO-8601格式中的duration&gt;"）</p><p>toDuration(&lt;持续时间（毫秒）)</p></td>
        <td><p><pre>toDuration("PT5S")// 5秒</pre></p>
        <p><pre>toDuration(500)// </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>—以“20.345秒”的形式分解</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> —“15分钟”</pre></p>
        <p><pre>（其中一分钟为60秒）</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>—作为“10小时”的解囊</pre></p>
        <p><pre>（其中一小时为3600秒）</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>—“2天”</pre></p>
        <p><pre>(其中， </pre></p>
        <p><pre>24小时或86400秒)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— Pars as</pre></p>
        <p><pre>“2天，3小时，4分钟”</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— Pars as</pre></p>
        <p><pre>"-6小时+3分钟"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— Pars as</pre></p>
        <p><pre>“-6小时-3分钟”</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— Pars as</pre></p>
        <p><pre>"+6小时-3分钟"</pre></p></td>
    </tr>
    <tr>
        <td>列表</td>
        <td>以逗号分隔的表达式列表，使用方括号作为分隔符。 不支持多态，因此列表中包含的所有表达式应具有相同类型。</td>
        <td>[&lt;表达式&gt;, &lt;表达式&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
