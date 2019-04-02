# ConfigLayer7BlackWhiteList {#reference609 .reference}

调用ConfigLayer7BlackWhiteList为指定域名设置7层防护黑白名单。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要配置的域名。|
|BlackList.N|String|否|黑名单列表。若有多个加黑地址，依次传入BlackList.1, BlackList.2, BlackList.3, ...|
|WhiteList.N|String|否|白名单列表。若有多个加白地址，依次传入WhiteList.1, WhiteList.2, WhiteList.3, ...|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "Domain": "www.alibaba.com",
  "BlackList.1" : "1.1.1.1",
  "BlackList.2" : "2.2.2.2/24",
  "WhiteList.1" : "3.3.3.3",
  "WhiteList.2" : "4.4.4.4/24"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

