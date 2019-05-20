# DescribeDdosEvent {#reference_265083 .reference}

调用DescribeDdosEvent接口查看指定防护包上的DDoS事件。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeDdosEvent。|
|EndTime|Integer|是|查询结束时间，秒级时间戳。|
|InstanceId|String|是|要查询的防护包实例ID。|
|PageNo|Integer|是|列表的页码，默认值为1。|
|PageSize|Integer|是|分页查询时每页的行数，最大值为50，默认值为10。|
|StartTime|Integer|是|查询开始时间，秒级时间戳。|
|Ip|String|否|要查询的防护对象IP。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Total|Long|DDoS事件总数。|
|Events|Array|DDoS事件信息。|
|└EndTime|Integer|攻击结束时间，秒级时间戳。|
|└Ip|String|被攻击的IP。|
|└Mbps|Integer|攻击流量大小。|
|└Pps|Integer|攻击报文数量。|
|└StartTime|Integer|攻击开始时间，秒级时间戳。|
|└Status|String|事件状态，取值： -   hole\_begin：黑洞中
-   hole\_end：黑洞结束
-   defense\_begin：清洗中
-   defense\_end：清洗结束

 |

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeDdosEvent
&InstanceId=ddosbgp-cn-x1
&StartTime=1557305044
&EndTime=1557909844
&PageNo=1
&PageSize=10
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeDdosEventResponse>
       <RequestId>0AA279B6-30A5-47CC-A40D-088A8817A043</RequestId>
       <Events>
           <Event>
               <Pps>0</Pps>
               <Status>defense_end</Status>
               <Ip>1.1.1.1</Ip>
               <Mbps>110000</Mbps>
               <EndTime>1557891306</EndTime>
               <StartTime>1557889506</StartTime>
           </Event>
       </Events>
       <Total>1</Total>
    </DescribeDdosEventResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "RequestId": "6A507DC8-F657-4C13-84E2-D1D1B9400753",
     "Events": [
       {
         "Pps": 0,
         "Status": "defense_end",
         "Ip": "1.1.1.1",
         "Mbps": 110000,
         "EndTime": 1557891306,
         "StartTime": 1557889506
       }
     ],
     "Total": 8
    }
    ```


