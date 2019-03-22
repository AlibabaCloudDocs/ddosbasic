# DescribeDomainConfigPage {#doc_api_1094372 .reference}

调用DescribeDomainConfigPage接口分页查询用户的网站配置列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=DDoSPro&api=DescribeDomainConfigPage)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainConfigPage|要执行的操作。取值：**DescribeDomainConfigPage**。

 |
|PageNo|Integer|是|1|分页页号，最小值为**1**。

 |
|PageSize|Integer|是|5|分页大小，最大值为**5**。

 |
|Domain|String|否|www.aliyun.com|要查询的域名。支持模糊查询。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigList| | |网站配置列表。

 |
|└Cname|String|xxxxxx.alicloudddos.com|高防Cname值。

 |
|└Domain|String|www.aliyun.com|被防护的域名。

 |
|└Instances| | |与域名配置关联的高防实例信息。

 |
|└InstanceId|String|ddosbag-xxxx-xxxx|高防实例ID。

 |
|└InstanceRemark|String|高防实例1|高防IP的实例备注。

 |
|└Rules| | |转发规则。

 |
|└Ip|String|1.1.1.1|高防实例IP。

 |
|└Line|String|CT|线路，取值：

 -   **MT**：移动
-   **CT**：电信
-   **CUT**：联通
-   **BGP**：BGP

 |
|└ProxyTypeList| |\["https", "http"\]|转发协议列表，取值：

 -   **http**
-   **https**
-   **websocket**
-   **websockets**

 |
|└RealServers| |\["2.2.2.2", "3.3.3.3"\]|源站列表。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|Total|Integer|10|配置总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDomainConfigPage
&Domain=www.aliyun.com
&PageNo=1
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainConfigPageResponse>
  <ConfigList>
    <element>
      <Cname>xxxxxxxxxxxxxx.alicloudddos.com</Cname>
      <Domain>www.aliyun.com</Domain>
      <Instances>
        <element>
          <InstanceId>ddosBag-cn-XXXXX</InstanceId>
          <Rules>
            <element>
              <Ip>3.3.3.3</Ip>
              <Line>CUT</Line>
              <ProxyTypeList>
                <element>http</element>
                <element>https</element>
              </ProxyTypeList>
              <RealServers>
                <element>1.1.1.1</element>
                <element>2.2.2.2</element>
              </RealServers>
            </element>
          </Rules>
        </element>
      </Instances>
    </element>
  </ConfigList>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <Total>6</Total>
</DescribeDomainConfigPageResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
	"ConfigList":[
		{
			"Cname":"xxxxxxxxxxxxxx.alicloudddos.com",
			"Domain":"www.aliyun.com",
			"Instances":[
				{
					"InstanceId":"ddosBag-cn-XXXXX",
					"Rules":[
						{
							"Ip":"3.3.3.3",
							"ProxyTypeList":[
								"http",
								"https"
							],
							"RealServers":[
								"1.1.1.1",
								"2.2.2.2"
							],
							"Line":"CUT"
						}
					]
				}
			]
		}
	],
	"Total":6
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

