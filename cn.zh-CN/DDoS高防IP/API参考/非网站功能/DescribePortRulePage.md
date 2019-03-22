# DescribePortRulePage {#doc_api_1094257 .reference}

调用DescribePortRulePage接口分页查询非网站转发规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribePortRulePage)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePortRulePage|要执行的操作。取值：**DescribePortRulePage**。

 |
|CurrentPage|Integer|否|1|分页页号，最小值为**1**。

 |
|Ip|String|否|1.1.1.1|要查询的高防实例IP。

 |
|PageSize|Integer|否|10|分页大小，最大值为**10**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Count|Integer|3|转发规则总数。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |
|RuleList| | |转发规则列表。

 |
|└BackPort|Integer|233|源站端口。

 |
|└BackProtocol|String|tcp|源站端口转发协议。

 |
|└FrontPort|Integer|233|转发端口。

 |
|└FrontProtocol|String|tcp|转发端口转发协议。

 |
|└Ip|String|2.2.2.2|高防实例IP。

 |
|└LbId|String|xxxxxxx-xxxx-xxxx-xxxxxxxx|高防IP策略修改标识，用于下发健康检查、会话保持、DDoS防护策略。

 |
|└LvsType|String|poll|LVS转发规则，取值：**poll**（轮询模式）。

 |
|└RealServer|String|1.1.1.1|源站IP列表。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribePortRulePage
&Ip=1.1.1.1
&CurrentPage=1
&PageSize=10
&FrontPort=233
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribePortRulePageResponse>
  <Count>3</Count>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <RuleList>
    <element>
      <BackPort>233</BackPort>
      <BackProtocol>tcp</BackProtocol>
      <FrontPort>233</FrontPort>
      <FrontProtocol>tcp</FrontProtocol>
      <Ip>2.2.2.2</Ip>
      <LbId>xxxxxxx-xxxx-xxxx-xxxxxxxx</LbId>
      <LvsType>poll</LvsType>
      <RealServer>1.1.1.1</RealServer>
    </element>
  </RuleList>
</DescribePortRulePageResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RuleList":[
		{
			"Ip":"2.2.2.2",
			"FrontPort":233,
			"RealServer":"1.1.1.1",
			"BackPort":233,
			"BackProtocol":"tcp",
			"LvsType":"poll",
			"LbId":"xxxxxxx-xxxx-xxxx-xxxxxxxx",
			"FrontProtocol":"tcp"
		}
	],
	"Count":3,
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

