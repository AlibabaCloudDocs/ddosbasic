# ConfigHealthCheck {#reference1542 .reference}

You can call this operation to configure layer 4 or layer 7 health check settings.

## Request parameters { .section}

|Name|Type|Required|Description|
|----|----|--------|-----------|
|InstanceId|String|Yes|The ID of the Anti-DDoS Pro instance that you want to change settings for.|
|ForwardProtocol|String|Yes|The forwarding protocol. Valid values: -   TCP \(Layer 4\)
-   UDP \(Layer 4\)
-   HTTP \(Layer 7\)

 |
|FrontendPort|Integer|Yes|The port for front-end connections.|
|HealthCheck|String|Yes|The HealthCheck objects represented as a JSON string. For more information, see [HealthCheck](#).|

|Name|Type|Required|Description|
|----|----|--------|-----------|
|Type|String|Yes|The listener protocol. Valid values: -   TCP: Layer 4
-   HTTP: Layer 7

 |
|Domain|String|No|In layer 7 health check, the domain name.|
|Uri|String|No|In layer 7 health check, the URI path.|
|Timeout|Integer|No|In layer 4 health check, the response timeout.|
|Port|Integer|No|In layer 4 health check, the port that is used to connect with the origin server.|
|Interval|Integer|No|In layer 4 health check, the time interval between health checks.|
|Up|Integer|No|In layer 4 health check, the healthy threshold.|
|Down|Integer|No|In layer 4 health check, the unhealthy threshold.|

## Response parameters { .section}

|Name|Type|Description|
|----|----|-----------|
|RequestId|String|The GUID generated by Alibaba Cloud for the request.|

## Examples { .section}

**Sample requests** 

```
{
  "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "ForwardProtocol": "tcp",
  "FrontendPort": 80,
  "HealthCheck": "{\"Type\":\"tcp\",\"Timeout\":10,\"Port\":80,\"Interval\":10,\"Up\":10,\"Down\":40}"
}
				
```

**Sample responses** 

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
				
```

