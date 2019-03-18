# DescribeDdosAttackEvents {#doc_api_1091515 .reference}

调用DescribeDdosAttackEvents接口查询高防IP的攻击事件。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosAttackEvents)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosAttackEvents|系统规定参数。取值：DescribeDdosAttackEvents。

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
|Data| | |攻击事件信息，包括事件总数和事件列表。

 |
|└EventList| | |攻击事件列表。

 |
|└AttackType|String|syn-flood|攻击类型，取值：

 -   **tcp-flood**
-   **udp-flood**
-   **icmp-flood**
-   **finrst-flood**

 |
|└EndTime|Long|1535019587000|攻击结束时间戳，单位为毫秒。

 |
|└Result|Integer|1|事件结果，取值：

 -   **0**：清洗中
-   **1**：清洗成功
-   **3**：黑洞结束

 |
|└StartTime|Long|1535018684000|攻击开始时间戳，单位为毫秒。

 |
|└TotalCount|Integer|4|事件总数。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosAttackEvents
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
<DescribeDdosAttackEvents>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <Data>
    <TotalCount>4</TotalCount>
    <EventList>
      <EndTime>1535019587000</EndTime>
      <StartTime>1535018684000</StartTime>
      <AttackType>syn-flood</AttackType>
      <Result>1</Result>
    </EventList>
  </Data>
</DescribeDdosAttackEvents>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"EventList":[
			{
				"Result":1,
				"AttackType":"syn-flood",
				"EndTime":1535019587000,
				"StartTime":1535018684000
			}
		],
		"TotalCount":4
	},
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

