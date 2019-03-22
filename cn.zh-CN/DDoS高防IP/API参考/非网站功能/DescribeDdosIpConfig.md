# DescribeDdosIpConfig {#doc_api_1094256 .reference}

调用DescribeDdosIpConfig接口分页查询高防IP防护配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosIpConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosIpConfig|要执行的操作。取值：**DescribeDdosIpConfig**。

 |
|Index|Integer|是|0|查询索引，从**0**开始。

 |
|PageSize|Integer|是|10|分页大小，最大值为**10**。

 |
|Ips.N|RepeatList|否|1.1.1.1|要查询的高防IP列表。若有多个IP，请依次传入Ips.1、Ips.2、Ips.3...

 **说明：** 若不传入该参数，则返回所有实例的配置。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataList| | |高防IP防护信息列表。

 |
|└Bandwidth|Integer|10000|基础带宽值。

 |
|└CleanStatus|Integer|0|高防实例IP的清洗状态，取值：

 -   **0**：正常
-   **1**：清洗中
-   **2**：黑洞中
-   **3**：延迟黑洞中

 |
|└ConfigDomainCount|Integer|0|已使用网站防护数。

 |
|└ConfigPortCount|Integer|0|已使用非网站防护数。

 |
|└ElasticBandwidth|Integer|10000|弹性带宽值。

 |
|└Ip|String|118.178.214.208|高防实例IP。

 |
|└LbId|String|133bd628-aa9f-11e8-bae4-2c9d1e2c4716-cn-hangzhou-dg-a01|高防IP策略修改标识，用于下发健康检查、会话保持、DDoS防护策略。

 |
|└Line|String|bgp|高防Ip线路，取值：

 -   **MT**：移动
-   **CT**：电信
-   **CUT**：联通
-   **BGP**：BGP

 |
|└Status|Integer|1|高防实例IP的当前状态，取值：

 -   **0**：创建中
-   **1**：正常
-   **2**：已过期

 |
|└TotalDefenseCount|Integer|0|历史防护攻击事件总数。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |
|Total|Integer|1|结果总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosIpConfig
&Ips.1=1.1.1.1
&Index=0
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosIpConfigResponse>
  <DataList>
    <element>
      <Bandwidth>10000</Bandwidth>
      <CleanStatus>0</CleanStatus>
      <ConfigDomainCount>0</ConfigDomainCount>
      <ConfigPortCount>0</ConfigPortCount>
      <ElasticBandwidth>10000</ElasticBandwidth>
      <Ip>118.178.214.208</Ip>
      <LbId>133bd628-aa9f-11e8-bae4-2c9d1e2c4716-cn-hangzhou-dg-a01</LbId>
      <Line>BGP</Line>
      <Status>1</Status>
      <TotalDefenseCount>0</TotalDefenseCount>
    </element>
  </DataList>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <Total>1</Total>
</DescribeDdosIpConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"DataList":[
		{
			"Ip":"118.178.214.208",
			"Status":1,
			"TotalDefenseCount":0,
			"ConfigDomainCount":0,
			"CleanStatus":0,
			"ConfigPortCount":0,
			"ElasticBandwidth":10000,
			"LbId":"133bd628-aa9f-11e8-bae4-2c9d1e2c4716-cn-hangzhou-dg-a01",
			"Line":"BGP",
			"Bandwidth":10000
		}
	],
	"Total":1
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

