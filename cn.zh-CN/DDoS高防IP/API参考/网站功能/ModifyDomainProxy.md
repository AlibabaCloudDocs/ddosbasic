# ModifyDomainProxy {#doc_api_950016 .reference}

调用ModifyDomainProxy接口修改网站防护的转发协议。

## 调试 {#apiExplorer .section}

单击[这里](https://api.aliyun.com/#product=DDoSPro&api=ModifyDomainProxy)在OpenAPI Explorer中进行可视化调试，并生成SDK代码示例。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|ProxyType.N|RepeatList|是|https|转发协议类型，取值：

 -   **http**
-   **https**
-   **websocket**
-   **websockets**

 **说明：** 若有多个协议类型，依次传入ProxyType.1, ProxyType.2, ProxyType.3, ...

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ModifyDomainProxy
&Domain=www.aliyun.com
&ProxyType=["http","https"]
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

