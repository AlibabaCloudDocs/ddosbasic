# ModifyRealServers {#doc_api_1091450 .reference}

调用ModifyRealServers接口修改网站防护配置中线路对应的源站。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=ModifyRealServers)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyRealServers|要执行的操作。取值：**ModifyRealServers**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Line|String|是|CUT|要操作的线路，取值：

 -   **BGP**：BGP线路
-   **CT**：电信
-   **CUT**：联通
-   **MT**：移动

 |
|RealServers.N|RepeatList|是|1.1.1.1|源站列表。

 **说明：** 若有多个源站，依次传入RealServer.1, RealServer.2, RealServer.3, ...

 |
|Type|String|是|IP|回源类型，取值：

 -   **IP**：回源到Ip
-   **DOMAIN**：回源到域名

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ModifyRealServers
&Domain=www.aliyun.com
&Line=BGP
&Type=IP
&RealServers=["1.1.1.1","2.2.2.2"]
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyRealServers>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</ModifyRealServers>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

