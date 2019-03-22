# DescribeBackSourceCidr {#doc_api_1092499 .reference}

调用DescribeBackSourceCidr接口查询高防回源网段地址。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeBackSourceCidr)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeBackSourceCidr|要执行的操作。取值：**DescribeBackSourceCidr**。

 |
|Line|String|否|bgp|要查询的线路类型。取值：

 -   **unicom**：中国联通
-   **telecom**：中国电信
-   **mobile**：中国移动
-   **bgp**：BGP线路

 |
|Region|String|否|hangzhou|要查询的地区。取值：

 **说明：** 当Line传入bgp时必需。

 -   **hangzhou**：杭州
-   **beijing**：北京
-   **shenzhen**：深圳

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CidrList| |\["180.97.165.0/24", "180.97.166.0/24"\]|高防回源网段列表，结构描述如下：

 -   **Cidr**，List类型，高防回源网段列表。

 |
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeBackSourceCidr
&Line=telecom
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeBackSourceCidrResponse>
  <CidrList>
    <Cidr>
      <element>180.97.165.0/24</element>
      <element>180.97.166.0/24</element>
    </Cidr>
  </CidrList>
  <requestId>480AC85F-2B2A-49A4-A2DA-BF98AA96E8D6</requestId>
</DescribeBackSourceCidrResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"requestId":"480AC85F-2B2A-49A4-A2DA-BF98AA96E8D6",
	"CidrList":{
		"Cidr":[
			"180.97.165.0/24",
			"180.97.166.0/24"
		]
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

