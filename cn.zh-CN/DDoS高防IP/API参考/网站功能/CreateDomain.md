# CreateDomain {#doc_api_1094364 .reference}

调用CreateDomain接口创建网站防护规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=CreateDomain)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateDomain|要执行的操作。取值：**CreateDomain**。

 |
|Domain|String|是|www.aliyun.com|添加要防护的域名。

 |
|ProxyType.N|RepeatList|是|http|转发类型，取值：

 -   **http**
-   **https**
-   **websocket**
-   **websockets**

 **说明：** 若有多个类型，依次传入ProxyType.1、ProxyType.2、ProxyType.3 ...

 |
|RealServer.N|RepeatList|是|1.1.1.1|源站列表。

 **说明：** 若有多个源站，依次传入RealServer.1、RealServer.2、RealServer.3 ...

 |
|Type|String|是|IP|选择回源类型，取值：

 -   **IP**：回源到Ip
-   **DOMAIN**：回源到域名

 |
|CcEnable|Boolean|否|true|是否开启CC攻击防护功能。

 |
|Ips.N|RepeatList|否|1.1.1.1|防护解析到的高防IP列表，最多支持6个IP。

 **说明：** 若有多个高防IP，依次传入Ips.1、Ips.2、Ips.3 ...

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=CreateDomain
&Domain=www.aliyun.com
&Ips=["1.1.1.1","2.2.2.2"]
&RealServer=["1.1.1.1","2.2.2.2"]
&Type=IP
&CcEnable=true
&ProxyType=["http","https"]
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateDomainResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</CreateDomainResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

