# DescribeDomains {#reference2637 .reference}

调用DescribeDomains查询7层转发规则。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|否|要查询的域名。|
|QueryDomainPattern|String|否|查询匹配模式。取值： -   fuzzy：模糊查询（默认）
-   exact：精确查询

 |
|Offset|Integer|是|开始索引位置，即从第几条结果开始显示。默认从0开始。|
|PageSize|Integer|是|分页大小，即每页显示多少条记录。最大值10。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Total|Integer|域名总数。|
|Domains|\[\]Domain|域名列表。具体结构描述见[Domain](#)。|

|名称|类型|描述|
|--|--|--|
|Domain|String|域名。|
|ProxyTypeList|\[\]String|协议类型列表。具体结构描述见[ProxyTypeList](#ProxyTypeList)。|
|RealServers|\[\]String|源站列表。|
|CcEnabled|Boolean|是否启用CC防护。|
|CcRuleEnabled|Boolean|是否启用CC规则。|
|CcTemplate|String|CC防护模板。|
|WhiteList|\[\]String|白名单IP列表。|
|BlackList|\[\]String|黑名单IP列表。|
|CertName|String|证书名称。|
|RealSevers|\[\]Layer7RealServer|源站列表。具体结构描述见[Layer7RealServer](#)。|

|名称|类型|描述|
|--|--|--|
|ProxyType|String|协议类型。取值： -   http
-   https
-   websocket
-   websockets

 |
|ProxyPorts|Integer|协议端口。|

|名称|类型|描述|
|--|--|--|
|RealServer|String|源站地址。|
|RsType|Integer|源站类型。取值： -   0：IP
-   1：域名

 |

## 示例 { .section}

**请求示例** 

```
{
  "Domain": "www.alibaba.com",
  "QueryDomainPattern": "fuzzy",
  "Offset":0,
  "PageSize":10
}
				
```

**返回示例** 

```
{
  "Total": 2,
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "Domains": [
  	{
		"Domain": "www.alibaba.com",
		"ProxyTypeList": [{
            		"ProxyType":"http",
           		"ProxyPorts":[
                			80,
                			8080
            				]
         	}],
		"RealServers": [{
			"RealServer": "1.1.1.1",
			"RsType":0
		},{
			"RealServer": "1.1.1.2",
			"RsType":1
			}
		],
		"CcEnabled" : false,
		"CcRuleEnabled" : true,
		"CcTemplate" : "default",
		"BlackList" : ["1.1.1.1/1","1.1.1.2/2"],
		"WhiteList" : ["1.1.1.1/1","1.1.1.2/2"],
		"CertName" : "www_alibaba_com.pem"
	},{
		"Domain": "www.alibaba.com",
		"ProxyTypeList": [{
            		"ProxyType":"http",
           		"ProxyPorts":[
                			80,
                			8080
            				]
         	}],
		"RealServers": [{
			"RealServer": "1.1.1.1",
			"RsType":0
		},{
			"RealServer": "1.1.1.2",
			"RsType":1
			}
		],
		"CcEnabled" : false,
		"CcRuleEnabled" : true,
		"CcTemplate" : "default",
		"BlackList" : ["1.1.1.1/1","1.1.1.2/2"],
		"WhiteList" : ["1.1.1.1/1","1.1.1.2/2"],
		"CertName" : "www_alibaba_com.pem"
	}
  ]
}
				
```

