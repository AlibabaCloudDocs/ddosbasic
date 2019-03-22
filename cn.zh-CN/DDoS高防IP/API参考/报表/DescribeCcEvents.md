# DescribeCcEvents {#doc_api_1094226 .reference}

调用DescribeCcEvents接口查询用户域名的CC攻击事件。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeCcEvents)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCcEvents|要执行的操作。取值：**DescribeCcEvents**。

 |
|Domain|String|否|www.aliyun.com|要查询的域名。

 |
|EndTime|Long|否|1534921519|查询结束时间戳，单位为秒。时间跨度不能超过30天。

 |
|PageNo|Integer|否|1|分页页号，最小值为**1**。

 |
|PageSize|Integer|否|10|分页大小，最大值为**20**。

 |
|StartTime|Long|否|1536891600|查询开始时间戳，单位为秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|EventList| | |攻击事件列表。

 |
|└AttackFinished|Boolean|true|攻击是否结束。

 |
|└BlockedCount|Integer|1041|攻击被阻断次数。

 |
|└Domain|String|www.aliyun.com|域名。

 |
|└Duration|Integer|3|攻击持续时长，单位小时

 |
|└EndTime|String|2018-08-23 10:29:00|攻击结束时间。

 |
|└MaxQps|Integer|274|峰值QPS。

 |
|└StartTime|String|2018-08-23 10:26:00|攻击开始时间。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |
|Total|Integer|3|攻击事件总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeCcEvents
&StartTime=1536891600
&EndTime=1534921519
&Domain=www.aliyun.com
&PageNo=1
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCcEventsResponse>
  <EventList>
    <element>
      <AttackFinished>true</AttackFinished>
      <BlockedCount>1041</BlockedCount>
      <Domain>www.aliyun.com</Domain>
      <Duration>3</Duration>
      <EndTime>2018-08-23 10:29:00</EndTime>
      <MaxQps>274</MaxQps>
      <StartTime>2018-08-23 10:26:00</StartTime>
    </element>
  </EventList>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <Total>3</Total>
</DescribeCcEventsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"EventList":[
		{
			"BlockedCount":1041,
			"Domain":"www.aliyun.com",
			"Duration":3,
			"MaxQps":274,
			"EndTime":"2018-08-23 10:29:00",
			"StartTime":"2018-08-23 10:26:00",
			"AttackFinished":true
		}
	],
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"Total":3
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

