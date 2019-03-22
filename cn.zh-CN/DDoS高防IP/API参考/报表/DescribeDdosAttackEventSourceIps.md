# DescribeDdosAttackEventSourceIps {#doc_api_1094225 .reference}

调用DescribeDdosAttackEventSourceIps接口查询高防IP攻击事件的源攻击IP列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosAttackEventSourceIps)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosAttackEventSourceIps|要执行的操作。取值：**DescribeDdosAttackEventSourceIps**。

 |
|CurrentPage|Integer|是|1|分页页号，最小值为**1**。

 |
|EndTime|Long|是|1536893404|查询结束时间戳，单位为毫秒。时间跨度不能超过30天。

 |
|Ip|String|是|1.1.1.1|要查询的高防实例IP。

 |
|PageSize|Integer|是|10|分页大小，最大值为**20**。

 |
|StartTime|Long|是|1536891600|查询开始时间戳，单位为毫秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |攻击源IP信息，包括总数和列表。

 |
|└IpList| | |攻击源IP列表。

 |
|└City|String|中国-辽宁省-大连市|攻击来源城市。

 |
|└InBps|Integer|65798144|攻击流量大小，单位Bps。

 |
|└SourceIp|String|2.2.2.2|攻击源IP。

 |
|└TotalCount|Integer|55|事件总数。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosAttackEventSourceIps
&StartTime=1536891600
&EndTime=1536893404
&Ip=1.1.1.1
&CurrentPage=1
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosAttackEventSourceIpsResponse>
  <Data>
    <IpList>
      <element>
        <City>中国-辽宁省-大连市</City>
        <InBps>65798144</InBps>
        <SourceIp>2.2.2.2</SourceIp>
      </element>
    </IpList>
    <TotalCount>55</TotalCount>
  </Data>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</DescribeDdosAttackEventSourceIpsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"TotalCount":55,
		"IpList":[
			{
				"City":"中国-辽宁省-大连市",
				"SourceIp":"2.2.2.2",
				"InBps":65798144
			}
		]
	},
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

