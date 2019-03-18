# ConfigSwitchPriority {#doc_api_1091476 .reference}

调用ConfigSwitchPriority接口修改网站防护中高防IP的调度优先级。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=ConfigSwitchPriority)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ConfigSwitchPriority|要执行的操作。取值：**ConfigSwitchPriority**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Config.N.Ip|String|否|1.1.1.1|高防实例IP。

 **说明：** 多值时依次传入Config.1.Ip, Config.2.Ip, Config.3.Ip, ...

 |
|Config.N.Priority|Integer|否|30|优先级大小，取值：1~999。取值越小优先级越高。

 **说明：** 多值时依次传入Config.1.Priority, Config.2.Priority, Config.3.Priority, ...

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ConfigSwitchPriority
&Domain=www.aliyun.com
&Config=[{"ip":"1.1.1.1","priority":50}]
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigSwitchPriority>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</ConfigSwitchPriority>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

