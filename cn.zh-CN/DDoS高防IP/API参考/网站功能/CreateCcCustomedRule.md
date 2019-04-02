# CreateCcCustomedRule {#doc_api_1094358 .reference}

调用CreateCcCustomedRule接口创建网站安全防护CC自定义规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=CreateCcCustomedRule)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateCcCustomedRule|要执行的操作。取值：**CreateCcCustomedRule**。

 |
|BlockingTime|Integer|是|60|设置阻断时间，单位为秒，取值范围：60~86,400。

 |
|BlockingType|String|是|captcha|选择阻断类型，取值：

 -   **captcha**：人机识别
-   **close**：封禁

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Interval|Integer|是|5|设置检测时长，单位为秒，取值范围：5~10,800。

 |
|MatchingRule|String|是|prefix|选择匹配规则，取值：

 -   **prefix**：前缀模式
-   **match**：完全匹配

 |
|Name|String|是|customeCcRule1|设置规则名称。

 |
|Uri|String|是|/a/b/c|设置防护路径。

 |
|VisitCount|Integer|是|2|允许单一IP的访问次数，取值范围：2~2,000。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=CreateCcCustomedRule
&Domain=www.aliyun.com
&Name=testCcRule1
&Uri=/a/b/c
&MatchingRule=prefix
&Interval=100
&BlockingType=captcha
&BlockingTime=100
&VisitCount=100
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateCcCustomedRuleResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</CreateCcCustomedRuleResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

