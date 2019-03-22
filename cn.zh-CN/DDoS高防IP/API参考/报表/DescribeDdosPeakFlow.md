# DescribeDdosPeakFlow {#doc_api_1094223 .reference}

调用DescribeDdosPeakFlow接口查询高防IP的攻击峰值。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosPeakFlow)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosPeakFlow|要执行的操作。取值：**DescribeDdosPeakFlow**。

 |
|Ip|String|是|1.1.1.1|要查询的高防实例IP。

 |
|EndTime|Long|否|1536893404|查询结束时间戳，单位为毫秒。

 |
|StartTime|Long|否|1536891600|查询开始时间戳，单位为毫秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PeakFlow|String|8.36|攻击峰值，单位为G。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosPeakFlow
&StartTime=1536891600
&EndTime=1536893404
&Ip=1.1.1.1
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosPeakFlowResponse>
  <PeakFlow>8.36</PeakFlow>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</DescribeDdosPeakFlowResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"PeakFlow":"8.36"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

