# DescribeBackSourceCidr {#reference489 .reference}

调用DescribeBackSourceCidr查询回源网段。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Line|String|是|要查询的防护线路。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|CidrList|\[\]String|回源IP段列表。|

## 示例 { .section}

**请求示例**

```
{
  "Line":"coop-line-001"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "CidrList" : ["47.97.128.0/25","47.97.128.128/25"]
}

```

