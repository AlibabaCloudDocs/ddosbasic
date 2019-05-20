# DescribePackIpList {#reference_265088 .reference}

调用DescribePackIpList接口查询防护包的防护IP列表信息。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribePackIpList。|
|InstanceId|String|是|要查询的防护包实例ID。|
|PageNo|String|是|列表的页码，默认值为1。|
|PageSize|Integer|是|分页查询时每页的行数，最大值为50，默认值为10。|
|Ip|Integer|否|要查询的防护对象IP，设置后只返回指定IP的信息。|
|ProductName|String|否|要查询的防护对象IP的归属产品类型，取值： -   ECS
-   SLB
-   EIP
-   WAF

 设置后只返回指定产品的防护IP信息。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Code|String|响应状态码。|
|Success|Boolean|是否成功调用请求。|
|Total|Integer|返回结果的数量。|
|IpList|Array|防护IP列表。|
|└Ip|String|被防护IP。|
|└Product|String|IP的归属产品，取值： -   ECS
-   SLB
-   EIP
-   WAF

 |
|└Remark|String|归属产品备注，比如ECS实例的备注。|
|└Status|String|IP的状态，取值： -   normal：正常
-   hole\_begin：黑洞中

 |

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribePackIpList
&InstanceId=ddosbgp-cn-x1
&PageNo=1
&PageSize=10
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribePackIpListResponse>
       <RequestId>8584D3B6-BB3C-441E-B1D6-E154ED25C032</RequestId>
       <IpList>
           <Ipitem>
               <Status>normal</Status>
               <Ip>1.1.1.1</Ip>
               <Product>ECS</Product>
               <Remark>test</Remark>
           </Ipitem>
       </IpList>
       <Success>true</Success>
       <Code>200</Code>
       <Total>1</Total>
    </DescribePackIpListResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "RequestId": "B479FE9B-F0EB-423B-81E5-ECE2167BCF40",
     "IpList": [
       {
         "Status": "normal",
         "Ip": "1.1.1.1",
         "Product": "ECS",
         "Remark": "test"
       }
     ],
     "Success": true,
     "Code": "200",
     "Total": 1
    }
    ```


