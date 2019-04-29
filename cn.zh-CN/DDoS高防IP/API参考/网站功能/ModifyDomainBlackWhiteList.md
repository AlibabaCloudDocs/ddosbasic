# ModifyDomainBlackWhiteList {#doc_api_DDoSPro_ModifyDomainBlackWhiteList .reference}

调用ModifyDomainBlackWhiteList接口修改网站安全防护的黑白名单。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=ModifyDomainBlackWhiteList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDomainBlackWhiteList|要执行的操作。取值：**ModifyDomainBlackWhiteList**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Black.N|RepeatList|否|2.2.2.2/24|传入黑名单IP或IP段列表。

 **说明：** 若传入空列表，则表示清空黑名单。多值时依次传入Black.1、Black.2、Black.3 ...

 |
|White.N|RepeatList|否|1.1.1.1/24|传入白名单IP或IP段列表。

 **说明：** 若传入空列表，则表示清空白名单。多值时依次传入White.1、White.2、White.3 ...

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ModifyDomainBlackWhiteList
&Domain=www.aliyun.com
&Black.1=2.2.2.2/24
&White.1=1.1.1.1/24
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyDomainBlackWhiteListResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</ModifyDomainBlackWhiteListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

