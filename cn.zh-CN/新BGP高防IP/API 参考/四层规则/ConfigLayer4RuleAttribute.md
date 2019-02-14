# ConfigLayer4RuleAttribute {#reference3370 .reference}

调用ConfigLayer4RuleAttribute配置4层转发规则属性，包括会话保持和DDoS防护策略。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|要操作的实例ID。|
|ForwardProtocol|String|是|转发协议，取值：TCP、UDP。|
|FrontendPort|Integer|是|前端端口。|
|Config|String|是|配置信息，传入TcpConfig或UdpConfig对象JSON串。TcpConfig的具体结构描述见[TcpConfig](#)，UdpConfig的具体结构描述见[UdpConfig](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|PersistenceTimeout|Integer|是|会话保持的超时时间，单位为秒。默认为0，表示关闭。|
|Synproxy|String|是|DDoS防护策略的虚假源，取值：off、on。|
|NodataConn|String|是|DDoS防护策略的空连接，取值：off、on。|
|Sla|Sla|是|目的限制配置。具体结构描述见[Sla](#)。|
|Slimit|Slimit|是|源限制配置。具体结构描述见[Slimit](#)。|
|PayloadLen|PayloadLen|是|包过滤配置。具体结构描述见[PayloadLen](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|PersistenceTimeout|Integer|是|会话保持的超时时间，单位为秒。默认为0，表示关闭。|
|Synproxy|String|是|DDoS防护策略的虚假源，取值：off、on。|
|NodataConn|String|是|DDoS防护策略的空连接，取值：off、on。|
|Sla|Sla|是|目的限制配置。具体结构描述见[Sla](#)。|
|Slimit|Slimit|是|源限制配置。具体结构描述见[Slimit](#)。|
|PayloadLen|PayloadLen|是|包过滤配置。具体结构描述见[PayloadLen](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|Cps|Integer|是|DDoS防护策略/目的新建连接限速，取值范围：100~100,000。|
|Maxconn|Integer|是|DDoS防护策略/目的并发连接限速，取值范围：1000~1,000,000。|
|CpsEnable|Integer|否|是否开启Cps，取值：-   0：禁用cps
-   1：启用cps（默认）

|
|MaxconnEnable|Integer|否|是否开启Maxconnection，取值：-   0：禁用maxconn
-   1：启用maxconn（默认）

|

|名称|类型|是否必需|描述|
|--|--|----|--|
|Cps|Integer|是|DDoS防护策略/源新建连接限速，取值范围：100~100,000。|
|Maxconn|Integer|是|DDoS防护策略/源并发连接限速，取值范围：1,000~1,000,000。|
|CpsEnable|Integer|否|是否开启Cps，取值：-   0：禁用cps
-   1：启用cps（默认）

|
|MaxconnEnable|Integer|否|是否开启Maxconnection，取值：-   0：禁用maxconn
-   1：启用maxconn（默认）

|

|名称|类型|是否必需|描述|
|--|--|----|--|
|Min|Integer|是|DDoS防护策略/包长度过滤，包长度的最小值。|
|Max|Integer|是|DDoS防护策略/包长度过滤，包长度的最大值。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "ForwardProtocol": "tcp",
  "FrontendPort": 80,
  "Config": "{\"PersistenceTimeout\":80,\"Synproxy\":\"off\",\"NodataConn\":\"off\",\"Sla\":{\"Cps\":10,\"Maxconn\":10},\"Slimit\":{\"Cps\":10,\"Maxconn\":30},\"PayloadLen\":{\"Min\":1,\"Max\":2}}"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

