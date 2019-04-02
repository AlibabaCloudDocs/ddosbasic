# CreatePortRule {#doc_api_1094251 .reference}

调用CreatePortRule接口创建非网站转发规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=CreatePortRule)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreatePortRule|要执行的操作。取值：**CreatePortRule**。

 |
|BackPort|Integer|否|255|设置源站端口。

 |
|FrontPort|Integer|否|255|设置转发端口。

 |
|Ip|String|否|1.1.1.1|要操作的高防实例IP。

 |
|ProxyType|String|否|tcp|设置转发协议，取值：

 -   **tcp**
-   **udp**

 |
|RealServerList|String|否|2.2.2.2,3.3.3.3|添加源站列表，以逗号分隔。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=CreatePortRule
&Ip=1.1.1.1
&FrontPort=255
&BackPort=255
&Protocol=tcp
&RealServerList=2.2.2.2,3.3.3.3
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreatePortRuleResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</CreatePortRuleResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

