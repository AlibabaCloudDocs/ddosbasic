# DescribeHealthCheckConfig {#doc_api_1094258 .reference}

调用DescribeHealthCheckConfig接口查询非网站转发健康检查类配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeHealthCheckConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeHealthCheckConfig|要执行的操作。取值：**DescribeHealthCheckConfig**。

 |
|Ip|String|是|1.1.1.1|要查询的高防IP。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Listeners| | |健康检查监听配置。

 |
|└BackPort|Integer|8080|源站端口。

 |
|└Check| | |健康检查配置信息。

 |
|└Domain|String|www.aliyun.com|（仅HTTP协议）域名。

 |
|└Down|Integer|7|不健康阈值。

 |
|└Interval|Integer|6|检查间隔。

 |
|└Port|Integer|8080|检查端口。

 |
|└Timeout|Integer|5|响应超时时间。

 |
|└Type|String|tcp|协议类型。

 |
|└Up|Integer|8|健康阈值。

 |
|└Uri|String|/login|（仅HTTP协议）检查路径。

 |
|└Config| | |DDoS防护策略。

 |
|└NoDataConn|String|off|虚假源开关。

 |
|└PayloadLength| | |包长度过滤，Min为最小值，Max为最大值。

 |
|└Max|Integer|6000|包长度最大值。

 |
|└Min|Integer|0|包长度最小值。

 |
|└PersistenceTimeout|Integer|900|会话保持检查时间，单位为秒。

 |
|└Sla| | |目的新建、并发链接配置。

 |
|└Cps|Integer|125|源新建连接限速。

 |
|└CpsEnable|Integer|1|源新建连接限速开关，取值：

 -   **0**：关闭
-   **1**：打开

 |
|└MaxConn|Integer|1226|源并发连接限速。

 |
|└MaxConnEnable|Integer|1|源并发连接限速开关，取值：

 -   **0**：关闭
-   **1**：打开

 |
|└Slimit| | |源新建、并发链接配置。

 |
|└Cps|Integer|123|源新建连接限速。

 |
|└CpsEnable|Integer|1|源新建连接限速开关，取值：

 -   **0**：关闭
-   **1**：打开

 |
|└MaxConn|Integer|124|源并发连接限速。

 |
|└MaxConnEnable|Integer|1|源并发连接限速开关，取值：

 -   **0**：关闭
-   **1**：打开

 |
|└SynProxy|String|on|空连接开关。

 |
|└FrontendPort|Integer|8080|转发端口。

 |
|└Protocol|String|tcp|协议。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeHealthCheckConfig
&Ip=1.1.1.1
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeHealthCheckConfigResponse>
  <Listeners>
    <element>
      <BackPort>8080</BackPort>
      <Check>
        <Down>7</Down>
        <Interval>6</Interval>
        <Port>8080</Port>
        <Timeout>5</Timeout>
        <Type>tcp</Type>
        <Up>8</Up>
      </Check>
      <Config>
        <NoDataConn>off</NoDataConn>
        <PayloadLength>
          <Max>6000</Max>
          <Min>0</Min>
        </PayloadLength>
        <PersistenceTimeout>900</PersistenceTimeout>
        <Sla>
          <Cps>125</Cps>
          <CpsEnable>1</CpsEnable>
          <MaxConn>1226</MaxConn>
          <MaxConnEnable>1</MaxConnEnable>
        </Sla>
        <Slimit>
          <Cps>123</Cps>
          <CpsEnable>1</CpsEnable>
          <MaxConn>124</MaxConn>
          <MaxConnEnable>1</MaxConnEnable>
        </Slimit>
        <SynProxy>on</SynProxy>
      </Config>
      <FrontendPort>8080</FrontendPort>
      <Protocol>tcp</Protocol>
    </element>
  </Listeners>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</DescribeHealthCheckConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Listeners":[
		{
			"Check":{
				"Down":7,
				"Port":8080,
				"Timeout":5,
				"Interval":6,
				"Up":8,
				"Type":"tcp"
			},
			"Config":{
				"PayloadLength":{
					"Max":6000,
					"Min":0
				},
				"SynProxy":"on",
				"Sla":{
					"MaxConnEnable":1,
					"MaxConn":1226,
					"Cps":125,
					"CpsEnable":1
				},
				"NoDataConn":"off",
				"Slimit":{
					"MaxConnEnable":1,
					"MaxConn":124,
					"Cps":123,
					"CpsEnable":1
				},
				"PersistenceTimeout":900
			},
			"FrontendPort":8080,
			"BackPort":8080,
			"Protocol":"tcp"
		}
	],
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

