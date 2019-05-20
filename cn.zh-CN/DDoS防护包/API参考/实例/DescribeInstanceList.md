# DescribeInstanceList {#reference_265085 .reference}

调用DescribeInstanceList接口查询防护包实例的详细信息。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeInstanceList。|
|PageNo|Integer|是|列表的页码，默认值为1。|
|PageSize|Integer|是|分页查询时每页的行数，最大值为50，默认值为10。|
|InstanceIdList|String|否|指定要查询的防护包实例ID，多个ID间用逗号分隔。以JSON数组串格式传入，例如，\['ddosbgp-cn-xx','ddosbpg-cn-xxx'\]。若不传入该参数，则返回所有防护包信息。|
|Remark|String|否|指定要查询的防护包实例的备注。若不传入该参数，则返回所有防护包信息。|
|IpVersion|String|否|指定要查询的防护包实例的防护IP类型，取值： -   IPv4
-   IPv6

 若不传入该参数，则返回所有防护包信息。|
|InstanceType|Integer|否|指定要查询的防护包实例的类型，取值： -   0：专业版
-   1：企业版

 若不传入该参数，则返回所有防护包信息。|
|Ip|String|否|指定要查询的防护包实例的防护对象IP。若不传入该参数，则返回所有防护包信息。|
|Orderby|String|否|排序字段，取值：expireTime（到期时间）。|
|Orderdire|String|否|排序方向，取值： -   desc：倒序
-   asc：顺序

 |

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Total|Long|返回结果的总数。|
|InstanceList|Array|防护包实例的详细信息。|
|└AutoRenewal|Boolean|是否开启自动续费。|
|└BlackholdingCount|String|防护包中正在黑洞中的IP数量。|
|└ExpireTime|Long|防护包的到期时间。|
|└GmtCreate|Long|防护包的创建时间。|
|└InstanceId|String|防护包实例ID。|
|└IpType|String|防护包的防护IP类型。|
|└Remark|String|防护包的备注。|
|└Status|String|防护包实例的状态，取值： -   1：正常
-   2：到期
-   3：释放

 |

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeInstanceList
&PageNo=1
&PageSize=10
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeInstanceListResponse>
       <RequestId>5DE4D6B1-8D6D-4AC3-84AF-5EE0A4C2778E</RequestId>
       <InstanceList>
           <Instance>
               <Status>1</Status>
               <AutoRenewal>true</AutoRenewal>
               <IpType>IPv4</IpType>
               <ExpireTime>1560009600000</ExpireTime>
               <InstanceId>ddosbgp-cn-xx</InstanceId>
               <GmtCreate>1554708159000</GmtCreate>
               <Remark>test</Remark>
               <BlackholdingCount>0</BlackholdingCount>
           </Instance>
       </InstanceList>
       <Total>1</Total>
    </DescribeInstanceListResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "RequestId": "C3F7E6AE-43B2-4730-B6A3-FD17552B8F65",
     "InstanceList": [
       {
         "Status": "1",
         "AutoRenewal": true,
         "IpType": "IPv4",
         "ExpireTime": 1560009600000,
         "InstanceId": "ddosbgp-cn-xx",
         "GmtCreate": 1554708159000,
         "Remark": "test",
         "BlackholdingCount": 0
       }
     ],
     "Total": 1
    }
    ```


