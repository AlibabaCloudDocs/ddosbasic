# DescribeDdosFlowProportionDiagram {#doc_api_1094228 .reference}

调用DescribeDdosFlowProportionDiagram接口查询高防IP的攻击比例图表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosFlowProportionDiagram)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosFlowProportionDiagram|要执行的操作。取值：**DescribeDdosFlowProportionDiagram**。

 |
|EndTime|Long|是|1536893404|查询结束时间戳，单位为毫秒。时间跨度不能超过30天。

 |
|Ip|String|是|1.1.1.1|要查询的高防实例IP。

 |
|StartTime|Long|是|1536891600|查询开始时间戳，单位为毫秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DropBps|Integer|27729882|攻击流量大小，单位为Bps。

 |
|DropPps|Integer|3264010|攻击数据包个数。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |
|TotalBps|Integer|27854138|总流量大小，单位Bps。

 |
|TotalPps|Integer|3374169|总数据包个数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosFlowProportionDiagram
&StartTime=1536891600
&EndTime=1536893404
&Ip=1.1.1.1
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosFlowProportionDiagramResponse>
  <DropBps>27729882</DropBps>
  <DropPps>3264010</DropPps>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <TotalBps>27854138</TotalBps>
  <TotalPps>3374169</TotalPps>
</DescribeDdosFlowProportionDiagramResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DropBps":27729882,
	"TotalBps":27854138,
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"TotalPps":3374169,
	"DropPps":3264010
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

