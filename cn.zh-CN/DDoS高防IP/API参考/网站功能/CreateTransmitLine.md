# CreateTransmitLine {#doc_api_1091445 .reference}

调用CreateTransmitLine接口添加网站防护转发线路。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=CreateTransmitLine)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateTransmitLine|系统规定参数。取值：CreateTransmitLine。

 |
|Domain|String|否|www.aliyun.com|要操作的域名。

 |
|Ips.N|RepeatList|否|1.1.1.1|高防IP列表。

 **说明：** 若有多个列表，依次传入Ips.1, Ips.2, Ips.3, ...

 |
|RealServers.N|RepeatList|否|2.2.2.2|源站列表。

 **说明：** 若有多个源站，依次传入RealServer.1, RealServer.2, RealServer.3, ...

 |
|Type|String|否|IP|回源类型，取值：

 -   **IP**：回源到Ip
-   **DOMAIN**：回源到域名

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=CreateTransmitLine
&Domain=www.aliyun.com
&Ips=["1.1.1.1","2.2.2.2"]
&RealServer=["1.1.1.1","2.2.2.2"]
&Type=IP
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<root>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</root>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

