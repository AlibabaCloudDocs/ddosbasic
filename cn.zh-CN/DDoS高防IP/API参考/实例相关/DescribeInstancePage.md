# DescribeInstancePage {#doc_api_1091281 .reference}

调用DescribeInstancePage接口查询高防IP的实例信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeInstancePage)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstancePage|系统规定参数。取值：DescribeInstancePage。

 |
|CurrentPage|Integer|否|1|分页页号，最小值为**1**。

 |
|InstanceId|String|否|ddosBag-cn-xxxxx|要查询的实例ID，优先级比**InstanceIdList**高。

 |
|InstanceIdList.N|RepeatList|否|ddosBag-cn-xxxxx|根据实例ID查询，传入要查询的高防实例ID。若有多个实例，依次传入InstanceIdList.1, InstanceIdList.2, InstanceIdList.3, ...

 **说明：** 该参数不为空时，则优先根据传入的实例ID进行查询。

 |
|IpList.N|RepeatList|否|1.1.1.1|根据高防IP查询，传入要查询的高防IP。若有多个高防IP，依次传入IpList.1, IpList.2, IpList.3, ...

 **说明：** 该参数优先级没有**InstanceIdList**高。若**InstanceIdList**为空，则根据传入的高防IP进行查询；否则，根据传入的**InstanceIdList**进行查询。

 |
|Line|String|否|CUT|要查询的线路，取值：

 -   **CUT**：联通
-   **CT**：电信

 |
|PageSize|Integer|否|10|分页大小，最大值为**10**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceList| | |实例信息列表。

 |
|└InstanceId|String|ddosBag-cn-xxxxx|高防实例ID。

 |
|└InstanceRemark|String|高防测试|高防实例备注。

 |
|└IpList| | |高防IP信息列表。

 |
|└BandWidth|Integer|10000|保底带宽值，单位为M。

 |
|└ElasticBandWidth|Integer|20000|弹性带宽值，单位为M。

 |
|└InstanceId|String|ddosBag-cn-xxxxx|高防IP地址，0表示未启用。

 |
|└Ip|String|1.1.1.1|高防实例的IP地址。

 |
|└Line|String|CUT|高防IP线路，取值：

 -   **CUT**：联通
-   **CT**：电信
-   **MT**：移动
-   **BGP**：BGP线路

 |
|└Status|Integer|1|高防实例状态，取值：

 -   **0**：创建中
-   **1**：正常
-   **2**：已过期

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |
|Total|Integer|1|查询到的结果总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeInstancePage
&CurrentPage=1
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstancePage>
  <InstanceList>
    <element>
      <InstanceId>ddosBag-cn-xxxxx</InstanceId>
      <InstanceRemark>高防测试</InstanceRemark>
      <IpList>
        <element>
          <BandWidth>10000</BandWidth>
          <ElasticBandWidth>20000</ElasticBandWidth>
          <InstanceId>ddosBag-cn-xxxxx</InstanceId>
          <Ip>1.1.1.1</Ip>
          <Line>CUT</Line>
          <Status>1</Status>
        </element>
      </IpList>
    </element>
  </InstanceList>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <Total>1</Total>
</DescribeInstancePage>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"InstanceList":[
		{
			"InstanceRemark":"高防测试",
			"InstanceId":"ddosBag-cn-xxxxx",
			"IpList":[
				{
					"Ip":"1.1.1.1",
					"Status":1,
					"BandWidth":10000,
					"ElasticBandWidth":20000,
					"InstanceId":"ddosBag-cn-xxxxx",
					"Line":"CUT"
				}
			]
		}
	],
	"Total":1
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

