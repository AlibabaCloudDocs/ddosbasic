# DescribeDdosAttackTypeChart {#doc_api_1094227 .reference}

调用DescribeDdosAttackTypeChart接口查询高防IP的攻击类型概览图表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosAttackTypeChart)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosAttackTypeChart|要执行的操作。取值：**DescribeDdosAttackTypeChart**。

 |
|EndTime|Long|是|1536891600|查询结束时间戳，单位为毫秒。

 |
|Ip|String|是|1.1.1.1|要查询的高防实例IP。

 |
|StartTime|Long|是|1536893404|查询开始时间戳，单位为毫秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AttckCount|Integer|6|攻击种类个数。

 |
|AttckType|String|udp-flood|攻击种类，取值：

 -   **tcp-flood**
-   **udp-flood**
-   **icmp-flood**
-   **finrst-flood**

 |
|DropCount|Integer|405322|清洗包大小，单位为Kbps。

 |
|DropType|String|udp|清洗的攻击种类。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosAttackTypeChart
&StartTime=1536891600
&EndTime=1536893404
&Ip=1.1.1.1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosAttackTypeChartResponse>
  <AttackCount>6</AttackCount>
  <AttackType>udp-flood</AttackType>
  <DropCount>405322</DropCount>
  <DropType>udp</DropType>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</DescribeDdosAttackTypeChartResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AttackType":"udp-flood",
	"DropType":"udp",
	"DropCount":405322,
	"AttackCount":6,
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

