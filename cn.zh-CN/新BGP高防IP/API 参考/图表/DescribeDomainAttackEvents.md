# DescribeDomainAttackEvents {#reference1573 .reference}

调用DescribeDomainAttackEvents查询指定域名的攻击事件。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要查询的域名。|
|StartTime|Long|是|流量查询的开始时间戳，单位：毫秒。|
|EndTime|Long|是|流量查询的结束时间戳，单位：毫秒。时间间隔最大30天。|
|Offset|Integer|是|返回结果开始位置，即从第几个结果开始返回。**说明：** 如不传入该参数，则从第0个结果开始返回。

|
|PageSize|Integer|是|分页大小，即每页显示多少条记录。最大值50。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|结果总数。|
|Events|\[\]DomainAttackEvent|域名攻击事件。具体结构描述见[DomainAttackEvent](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|StartTime|Long|事件开始时间，单位：毫秒。|
|EndTime|Long|事件结束时间，单位：毫秒|
|Duration|Integer|事件持续时间，单位：分。|
|Finished|Boolean|攻击是否结束。|
|MaxQps|Integer|最大攻击QPS。|
|BlockCount|Long|拦截的请求数量。|

## 示例 { .section}

**请求示例**

```
{
  "Domain": "alibaba.com",
  "StartTime": 3289457324,
  "EndTime": 3289457398,
  "Offset": 0,
  "PageSize": 10
}

```

**返回示例**

```
{
  "Total": 1,
  "Events": [
    {
      "StartTime": 3289457324,
      "EndTime": 3289457398,
      "Duration": 12,
      "Finished": True,
      "MaxQps": 800,
      "BlockCount": 2340823,
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

