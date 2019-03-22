# ModifyDDoSProtectConfig {#doc_api_1094253 .reference}

调用ModifyDDoSProtectConfig接口修改DDoS防护配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=ModifyDDoSProtectConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDDoSProtectConfig|要执行的操作。取值：**ModifyDDoSProtectConfig**。

 |
|ConfigJson|String|是|\{"payload\_len":\{"min":0,"max":6000\},"synproxy":"on","slimit":\{"pps":0,"maxconn\_enable":1,"bps":0,"maxconn":124,"cps":123,"cps\_enable":1\},"sla":\{"pps":0,"maxconn\_enable":1,"outbps":536870912,"cps":125,"maxconn":1226,"inbps":0,"cps\_enable":1\},"nodata\_conn":"off"\}|DDoS防护配置内容（JSON字符串格式），具体结构描述如下：

 -   **check**，Object类型，必选，DDoS防护策略配置，具体结构描述如下：

**说明：** 该参数名以小写开头。

    -   **PayloadLength**，Object类型，包长度过滤，具体结构描述如下：
        -   **Min**，Integer类型，必选，包长度最小值。
        -   **Max**，Integer类型，必选，包长度最大值。
    -   **PersistenceTimeout**，Integer类型，必选，会话保持检查时间，单位为秒。
    -   **NoDataConn**，String类型，必选，虚假源开关。
    -   **SynProxy**，String类型，必选，空连接开关。
    -   **Sla**，Object类型，必选，目的新建、并发链接配置，具体结构描述如下：
        -   **MaxConnEnable**，Integer类型，必选，目的并发连接限速开关，取值：
            -   **0**：关闭
            -   **1**：打开
        -   **MaxConn**，Integer类型，必选，目的并发连接限速。
        -   **CpsEnable**，Integer类型，必选，目的新建连接限速开关，取值：
            -   **0**：关闭
            -   **1**：打开
        -   **Cps**，Integer类型，必选，目的新建连接限速。
    -   **Slimit**，Object类型，必选，源新建、并发链接配置，具体结构描述如下：
        -   **MaxConnEnable**，Integer类型，必选，源并发连接限速开关，取值：
            -   **0**：关闭
            -   **1**：打开
        -   **MaxConn**，Integer类型，必选，源并发连接限速。
        -   **CpsEnable**，Integer类型，必选，源新建连接限速开关，取值：
            -   **0**：关闭
            -   **1**：打开
        -   **Cps**，Integer类型，必选，源新建连接限速。

 |
|FrontPort|Integer|是|255|转发端口。

 |
|Ip|String|是|1.1.1.1|要操作的高防实例IP。

 |
|LbId|String|否|xxxxxxx-xxxx-xxxx-xxxxxxxx|高防IP策略修改标识。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ModifyHealthCheckConfig
&Ip=1.1.1.1
&FrontPort=255
&LbId=xxxxxxx-xxxx-xxxx-xxxxxxxx
&ConfigJson={"payload_len":{"min":0,"max":6000},"synproxy":"on","slimit":{"pps":0,"maxconn_enable":1,"bps":0,"maxconn":124,"cps":123,"cps_enable":1},"sla":{"pps":0,"maxconn_enable":1,"outbps":536870912,"cps":125,"maxconn":1226,"inbps":0,"cps_enable":1},"nodata_conn":"off"}
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyHealthCheckConfigResponse>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
</ModifyHealthCheckConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

