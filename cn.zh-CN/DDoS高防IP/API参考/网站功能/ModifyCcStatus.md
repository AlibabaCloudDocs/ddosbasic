# ModifyCcStatus {#doc_api_1094370 .reference}

调用ModifyCcStatus接口启用或禁用网站安全CC攻击防护功能。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=ModifyCcStatus)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyCcStatus|要执行的操作。取值：**ModifyCcStatus**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Enable|Boolean|是|true|设置CC攻击防护开关状态。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ModifyCcStatus
&Domain=www.aliyun.com
&Enable=true
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCcStatusResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</ModifyCcStatusResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

