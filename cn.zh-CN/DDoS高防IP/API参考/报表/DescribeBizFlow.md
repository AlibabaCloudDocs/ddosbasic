# DescribeBizFlow {#doc_api_949104 .reference}

调用DescribeBizFlow接口查询高防IP上的业务流量信息，包括入方向和出方向流量。

## 调试 {#apiExplorer .section}

单击[这里](https://api.aliyun.com/#product=DDoSPro&api=DescribeBizFlow)在OpenAPI Explorer中进行可视化调试，并生成SDK代码示例。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EndTime|Long|是|1536498197|查询结束时间戳，单位为秒。

 |
|Ip|String|是|1.1.1.1|要查询的高防IP。

 |
|StartTime|Long|是|1536496397|查询开始时间戳，单位为秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |流量查询结果。

 **说明：** 您可以根据该结果进行图表绘制。

 |
|└InKbps| |\[1,1,1,1,1,1\]|入流量查询结果列表，每个数据为该时间点上的入流量大小，单位为Kbps。

 **说明：** 该数据对应的时间点可以根据**TimeScope**信息进行计算。

 |
|└OutKbps| |\[1,1,1,1,1,1\]|出流量查询结果列表，每个数据为该时间点上的出流量大小，单位为Kbps。

 **说明：** 该数据对应的时间点可以根据**TimeScope**信息进行计算。

 |
|└TimeScope| | |时间范围信息。

 |
|└Interval|Integer|60|流量点列表中相邻两个点的时间差，单位为秒。

 |
|└StartTime|Long|1536496397|查询开始时间戳，单位为秒。

 |
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeBizFlow
&EndTime=1536498197
&Ip=1.1.1.1
&StartTime=1536496397
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeBizFlow>
  <requestId>C8B26B44-0189-443E-9816-D951F59623A9</requestId>
  <Data>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>4</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>2</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>1</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>1</InKbps>
    <InKbps>0</InKbps>
    <InKbps>0</InKbps>
    <InKbps>2</InKbps>
    <InKbps>0</InKbps>
    <TimeScope>
      <Interval>60</Interval>
      <StartTime>1536496380</StartTime>
    </TimeScope>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
    <OutKbps>0</OutKbps>
  </Data>
</DescribeBizFlow>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"InKbps":[
			0,
			1,
			1,
			0,
			0,
			1,
			1,
			0,
			1,
			4,
			0,
			1,
			1,
			0,
			1,
			2,
			0,
			1,
			1,
			1,
			0,
			0,
			1,
			0,
			1,
			0,
			1,
			0,
			0,
			2,
			0
		],
		"TimeScope":{
			"Interval":60,
			"StartTime":1536496380
		},
		"OutKbps":[
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0,
			0
		]
	},
	"requestId":"C8B26B44-0189-443E-9816-D951F59623A9"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

