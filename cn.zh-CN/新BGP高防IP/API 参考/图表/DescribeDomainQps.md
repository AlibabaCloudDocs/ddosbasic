# DescribeDomainQps {#reference878 .reference}

调用DescribeDomainQps查询指定域名的QPS。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要查询的域名。|
|StartTime|Long|是|开始时间戳，单位：毫秒。|
|EndTime|Long|是|结束时间戳，单位：毫秒。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Interval|Long|相隔两个数据之间的时间差。|
|StartTime|Long|开始时间戳，单位：毫秒。|
|Totals|\[\]Long|总的QPS。|
|Blocks|\[\]Long|攻击QPS。|

## 示例 { .section}

**请求示例**

```
{
  "Domain": "www.alibaba.com",
  "StartTime": 23084000,
  "EndTime": 230842000
}

```

**返回示例**

```
{
  "Interval": 20384,
  "StartTime": 1525708800000,
  "Totals": [10,40,20],
  "Blocks": [20,30,20],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

