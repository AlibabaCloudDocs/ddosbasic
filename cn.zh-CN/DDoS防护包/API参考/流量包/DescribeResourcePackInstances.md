# DescribeResourcePackInstances {#reference_265092 .reference}

调用DescribeResourcePackInstances接口查询抗D流量包信息。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeResourcePackInstances。|
|CurrentPage|Integer|是|列表的页码，默认值为1。|
|PageSize|Integer|是|分页查询时每页显示的行数，最大值为50，默认值为10。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|TotalCount|Integer|返回结果的总数。|
|ResourcePacks|Array|抗D流量包信息。|
|└CurrCapacity|Long|可用防护流量，单位为Byte。|
|└EndTime|Long|失效时间。|
|└InitCapacity|Long|初始防护流量，单位为Byte。|
|└ResourcePackId|String|抗D流量包ID。|
|└StartTime|Long|生效时间。|
|└Status|Integer|流量包的状态，取值： -   closed：失效
-   valid：有效

 |

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeResourcePackInstances
&CurrentPage=1
&PageSize=10
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeResourcePackInstancesResponse>
       <TotalCount>1</TotalCount>
       <ResourcePacks>
           <ResourcePack>
               <Status>valid</Status>
               <ResourcePackId>DDOSFLOWBAG-cn-xx</ResourcePackId>
               <InitCapacity>100000000000000</InitCapacity>
               <EndTime>1649433600000</EndTime>
               <StartTime>1554708226000</StartTime>
               <CurrCapacity>0</CurrCapacity>
           </ResourcePack>
       </ResourcePacks>
       <RequestId>D8845F7B-6DE2-4904-A765-8C2BC409E678</RequestId>
    </DescribeResourcePackInstancesResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "TotalCount": 1,
     "ResourcePacks": [
       {
         "Status": "valid",
         "ResourcePackId": "DDOSFLOWBAG-cn-o4012thfl000b5",
         "InitCapacity": 100000000000000,
         "EndTime": 1649433600000,
         "StartTime": 1554708226000,
         "CurrCapacity": 0
       }
     ],
     "RequestId": "40B322C3-464E-477F-B137-46E64349F0E9"
    }
    ```


