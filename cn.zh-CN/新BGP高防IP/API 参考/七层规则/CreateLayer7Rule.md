# CreateLayer7Rule {#reference1425 .reference}

调用CreateLayer7Rule创建7层转发规则。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要添加的域名。|
|RsType|Integer|是|源站类型，取值：-   0：IP
-   1：域名

|
|InstanceIds.N|String|否|要绑定的实例Id。若有多个实例，依次传入InstanceIds.1, InstanceIds.2, InstanceIds.3, ..**说明：** 若不传入该参数，则只添加域名，不绑定到具体IP。

|
|Rules|String|是|传入7层规则Layer7Rule数组JSON串。具体结构描述见[Layer7Rule](#)。|

|名称|类型|描述|
|--|--|--|
|ProxyRules|\[\]ProxyRule|规则对象数组。具体结构描述见[ProxyRule](#)。|
|ProxyType|String|协议类型，取值：-   http
-   https
-   websocket
-   websockets

|

|名称|类型|描述|
|--|--|--|
|ProxyPort|Integer|协议端口，取值：80、443。|
|RealServers|\[\]String|用户源站。例如，1.1.1.1:443。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "Domain": "www.alibaba.com",
  "RsType": 1,
  "InstanceIds.1": "xxxx",
  "Rules": "[{\"ProxyRules\":[{\"ProxyPort\":443,\"RealServers\":[\"1.1.1.1:443\"]}],\"ProxyType\":\"https\"},{\"ProxyRules\":[{\"ProxyPort\":80,\"RealServers\":[\"1.1.1.1:80\"]}],\"ProxyType\":\"http\"}]"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

