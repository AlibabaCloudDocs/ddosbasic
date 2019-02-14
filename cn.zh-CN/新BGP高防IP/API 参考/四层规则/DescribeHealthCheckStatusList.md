# DescribeHealthCheckStatusList {#reference2049 .reference}

调用DescribeHealthCheckStatusList查询健康检查状态。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Listeners|String|是|要查询的转发规则Listeners数组（JSON字符串），每个Listener的具体结构描述见[Listener](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|实例ID。|
|Protocol|String|是|协议类型。|
|FrontendPort|Integer|是|前端使用的端口，范围：0-65535。|
|BackendPort|Integer|否|后端使用的端口，范围：0-65535。|
|RealServers|Json数组|否|源站IP地址。|
|IsAutoCreate|Boolean|否|是否自动创建。如果是，则不允许删除和修改。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|HealthCheckStatusList|HealthCheckStatus|健康检查状态列表。具体结构描述见[HealthCheckStatus](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例Id。|
|Protocol|String|协议类型。|
|FrontendPort|Integer|前端端口。|
|RealServerStatusList|RealServerStatus|源站状态JSON数组。具体结构描述见[RealServerStatus](#)。|
|Status|String|状态，取值：normal、abnormal。|

|名称|类型|描述|
|--|--|--|
|Address|String|源站IP。|
|Status|String|状态，取值：normal、abnormal。|

## 示例 { .section}

**请求示例**

```
{
  "Listeners": "[{\"InstanceId\":\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\",\"Protocol\":\"tcp\",\"FrontendPort\":80}]"
}

```

**返回示例**

```
{
  "HealthCheckStatusList": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "Protocol": "tcp",
      "FrontendPort": 80,
	  "Status": "normal",
	  "RealServerStatusList": [
        "Status": "normal",
        "Address": "1.1.1.1"
      ]
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

