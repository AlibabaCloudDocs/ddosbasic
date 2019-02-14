# DescribeInstanceStatistics {#reference999 .reference}

调用DescribeInstanceStatistics查询指定实例的统计信息。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceIds|String|是|要查询的实例ID数组（JSON字符串）。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|InstanceStatistics|InstanceStatistic|实例统计信息列表。具体结构描述见[InstanceStatistic](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|PortUsage|Integer|已使用4层规则的数量。|
|DomainUsage|Integer|已使用域名的数量。|

## 示例 { .section}

**请求示例**

```
{
  "InstanceIds": "[\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\",\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\"]"
}

```

**返回示例**

```
{
  "InstanceStatistics": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "PortUsage": 20,
      "DomainUsage": 10
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

