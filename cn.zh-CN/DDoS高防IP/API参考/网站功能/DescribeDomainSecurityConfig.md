# DescribeDomainSecurityConfig {#doc_api_1094366 .reference}

调用DescribeDomainSecurityConfig接口查询用户域名的安全防护配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDomainSecurityConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainSecurityConfig|要执行的操作。取值：**DescribeDomainSecurityConfig**。

 |
|Domain|String|否|www.aliyun.com|要查询的域名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BlackList|String|1.1.1.1,2.2.2.2|黑名单列表。

 |
|CcInfo| | |CC防护配置信息。

 |
|└CcCustomRuleCount|Integer|10|CC自定义规则总数。

 |
|└CcCustomRuleEnable|Boolean|true|CC自定义规则功能开关。

 |
|└CcSwitch|Boolean|true|CC攻击防护功能开关。

 |
|└CcTemplate|String|danger|CC防护模式，取值：

 -   **default**：正常
-   **gf\_under\_attack**：攻击紧急
-   **gf\_sos\_verify**：严格
-   **gf\_sos\_enhance**：非常严格

 |
|CnameEnable|Boolean|true|Cname开关。

 |
|CnameMode|Integer|1|调度模式，取值：

 -   **0**：优先级方式
-   **1**：负载均衡方式

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|WhiteList|String|1.1.1.1,2.2.2.2|白名单列表。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDomainSecurityConfig
&Domain=www.aliyun.com
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainSecurityConfigResponse>
  <BlackList>1.1.1.1,2.2.2.2</BlackList>
  <CcInfo>
    <CcCustomRuleCount>10</CcCustomRuleCount>
    <CcCustomRuleEnable>true</CcCustomRuleEnable>
    <CcSwitch>true</CcSwitch>
    <CcTemplate>danger</CcTemplate>
  </CcInfo>
  <CnameEnable>true</CnameEnable>
  <CnameMode>0</CnameMode>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <WhiteList>1.1.1.1,2.2.2.2</WhiteList>
</DescribeDomainSecurityConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"CcInfo":{
		"CcSwitch":true,
		"CcCustomRuleCount":10,
		"CcTemplate":"danger",
		"CcCustomRuleEnable":true
	},
	"CnameMode":0,
	"BlackList":"1.1.1.1,2.2.2.2",
	"CnameEnable":true,
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"WhiteList":"1.1.1.1,2.2.2.2"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

