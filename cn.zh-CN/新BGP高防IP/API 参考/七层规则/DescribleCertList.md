# DescribleCertList {#reference554 .reference}

调用DescribleCertList查询所有证书列表。

## 请求参数 { .section}

无

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|CertList|\[\]CertItem|证书列表。具体结构描述见[CertItem](#)。|

|名称|类型|描述|
|--|--|--|
|Id|Integer|证书ID。|
|Name|String|证书名称。|

## 示例 { .section}

**请求示例**

无

**返回示例**

```
{
    "CertList": [
        {
            "Id": 80,
			"Name" : "name1"
        },
		{
            "Id": 81,
			"Name" : "name2"
        }
    ]
}

```

