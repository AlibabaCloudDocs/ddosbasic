# DescribeIpTraffic {#reference1844 .reference}

调用DescribeIpTraffic查询指定IP的流量信息。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Eip|String|是|要查询的EIP地址。|
|Port|Integer|否|要查询的端口。**说明：** 若不传入该参数，则查询EIP下所有端口的流量。

|
|StartTime|Long|是|开始时间戳（秒）。|
|EndTime|Long|是|结束时间戳（秒）。|
|Interval|Integer|是|采样间隔（秒），必须是60秒的倍数，默认值60s。采样结果可缩放。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|MaxInBps|Long|最大入带宽，单位：bps。|
|AvgInBps|Long|平均入带宽，单位：bps。|
|MaxOutBps|Long|最大出带宽，单位：bps。|
|AvgOutBps|Long|平均出带宽，单位：bps。|
|IpTrafficPoints|IpTrafficPoint|具体的时间点列表。具体结构描述见[IpTrafficPoint](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|Time|Long|时间点（时间戳），单位：秒。|
|MaxInBps|Long|最大入带宽，单位：bps。|
|MaxOutBps|Long|最大出带宽，单位：bps。|
|Cps|Integer|连接新建速率。|
|ActConns|Integer|活跃的并发连接数。|
|InactConns|Integer|非活跃的并发连接数。|

## 示例 { .section}

**请求示例**

```
{
  "Eip": "1.1.1.1",
  "StartTime": 23084,
  "EndTime": 230842,
  "Interval": 60
}

```

**返回示例**

```
{
  "InBytes": 20384,
  "MaxInBps": 25321,
  "AvgInBps": 16324,
  "Outbytes": 230842,
  "MaxOutBps": 12345,
  "AvgOutBps": 12121,
  "IpTrafficPoints": [
    {
      "Time": 923493724,
	  "MaxInBps": 23420,
      "AvgInBps": 230843280,
      "MaxOutBps": 20348038,
      "AvgOutBps": 20283402834,
	  "Cps":123,
	  "ActConns": 234,
	  "InactConns":345
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

