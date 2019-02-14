# DescribeDomainAccessMode {#reference947 .reference}

调用DescribeDomainAccessMode查询域名的接入模式。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|DomainList|\[\]String|是|要查询的域名数组。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|DomainModeList|\[\]Object|模式配置。具体结构描述见[DomainModeList](#)。|

|名称|类型|描述|
|--|--|--|
|Domain|String|域名。|
|AccessMode|Integer|接入模式，取值：-   0：A记录
-   1：高防
-   2：回源

|

## 示例 { .section}

**请求示例**

```
{
  "DomainList": ["www.alibaba.com","www.aliyun.com"]
}

```

**返回示例**

```
{
    "RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
    "DomainModeList":[
        {
            "Domain":"www.alibaba.com",
            "AccessMode":1
        },
        {
            "Domain":"www.aliyun.com",
            "AccessMode":2
        }
    ]
}

```

