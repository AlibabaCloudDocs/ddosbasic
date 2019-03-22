# ModifyHealthCheckConfig {#doc_api_1094255 .reference}

调用ModifyHealthCheckConfig接口修改健康检查配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=ModifyHealthCheckConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyHealthCheckConfig|要执行的操作。取值：**ModifyHealthCheckConfig**。

 |
|ConfigJson|String|是|\{"check":\{"interval":5,"port":255,"timeout":5,"type":"http","up":3,"down":3,"domain":"www.aliyun.com","uri":"/a/a/a"\}\}|健康检查配置内容（JSON字符串格式），具体结构描述如下：

 -   **check**，Object类型，必选，健康检查内容配置，具体结构描述如下：

**说明：** 该参数名以小写开头。

    -   **interval**，Integer类型，必选，检查间隔。
    -   **port**，Integer类型，可选，检测端口。

**说明：** 协议为**tcp**或**udp**时必填。

    -   **timeout**，Integer类型，必选，响应超时时间。
    -   **type**，String类型，必选，协议类型，取值：
        -   **tcp**
        -   **udp**
        -   **http**
    -   **up**，Integer类型，必选，健康阈值。
    -   **down**，Integer类型，必选，不健康阈值。
    -   **domain**，String类型，可选，域名。

**说明：** 协议为**http**时可填，非必需。

    -   **uri**，String类型， 可选，检查路径。

**说明：** 协议为http时必填。


 |
|FrontPort|Integer|是|255|转发端口。

 |
|Ip|String|是|1.1.1.1|要操作的高防实例IP。

 |
|LbId|String|否|xxxxxxx-xxxx-xxxx-xxxxxxxx|高防IP策略修改标识。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ModifyHealthCheckConfig
&Ip=1.1.1.1
&FrontPort=255
&LbId=xxxxxxx-xxxx-xxxx-xxxxxxxx
&ConfigJson={"check":{"interval":5,"port":255,"timeout":5,"type":"http","up":3,"down":3,"domain":"www.aliyun.com","uri":"/a/a/a"}}
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyHealthCheckConfigResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</ModifyHealthCheckConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

