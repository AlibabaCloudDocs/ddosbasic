# DescribeOpEntities {#reference1760 .reference}

调用DescribeOpEntities查询操作日志。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|StartTime|Long|是|开始时间时间戳，单位：毫秒。|
|EndTime|Long|是|结束时间时间戳，单位：毫秒。|
|PageNo|Integer|是|页号，即从第几页开始显示。|
|PageSize|Integer|是|分页大小，即每页显示多少条结果。最大值50。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|记录总数。|
|OpEntities|OpEntity|操作日志。具体结构描述见[OpEntity](#)。|

|名称|类型|描述|
|--|--|--|
|GmtCreate|Long|创建日志的时间戳，单位：毫秒。|
|EntityType|Integer|操作对象类型。取值：1（IP类型）。|
|EntityObject|String|操作对象的值，即操作的IP地址。|
|OpAction|Integer|操作类型。取值：1（修改弹性带宽）。|
|OpAccount|String|操作人。|
|OpDesc|String|操作详情。OpDesc的JSON字符串，具体结构描述见[OpDesc](#)。|

|名称|类型|描述|
|--|--|--|
|oldValue|EntityValue|旧值。具体结构描述见[EntityValue](#)。|
|newValue|EntityValue|新值。具体结构描述见[EntityValue](#)。|

|名称|类型|描述|
|--|--|--|
|elasticBandwidth|Integer|弹性带宽值。|

## 示例 { .section}

**请求示例**

```
{
  "StartTime": 123,
  "EndTime": 456,
  "PageNo": 1,
  "PageSize": 10
}

```

**返回示例**

```
{
  "Total": 10,
  "OpEntities": [
    {
      "gmtCreate": 1120384，
      "entityObject": "1.1.1.1",
      "opAction": 2,
      "opDesc": {
	    "oldValue": {
		  "elasticBandwidth": 10
		},
		"newValue": {
		  "elasticBandwidth": 30
		}
	  },
      "opResult": 1
    }
  ]
}

```

