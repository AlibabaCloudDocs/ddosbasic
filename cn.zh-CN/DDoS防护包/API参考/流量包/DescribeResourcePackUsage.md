# DescribeResourcePackUsage {#reference_265094 .reference}

调用DescribeResourcePackUsage接口查询抗D流量包的使用明细。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeResourcePackUsage。|
|EndTime|Long|是|查询结束时间，秒级时间戳。所设置的查询时间区间不能超过30天。|
|StartTime|Long|是|查询开始时间，秒级时间戳。所设置的查询时间区间不能超过30天。|
|InstanceId|String|否|要查询的防护包实例ID。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|EndTime|Long|统计结束时间，秒级时间戳。|
|Interval|Long|统计时间间隔，单位为秒。|
|StartTime|Long|统计起始时间，秒级时间戳。|
|PackUsages|Array|已用防护流量明细。|
|└Time|Long|时间。|
|└Traffic|Float|流量，单位为Gb。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeResourcePackUsage
&InstanceId=ddosbgp-cn-x1
&StartTime=1557305044
&EndTime=1557909844
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeResourcePackUsageResponse>
       <Interval>3600</Interval>
       <PackUsages>
           <PackUsage>
               <Time>1557471600</Time>
               <Traffic>153.064</Traffic>
           </PackUsage>
       </PackUsages>
       <RequestId>694BB7DF-8AEB-4CF7-B0E9-1326C2D82A79</RequestId>
       <EndTime>1557910800</EndTime>
       <StartTime>1557302400</StartTime>
    </DescribeResourcePackUsageResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "Interval": 3600,
     "PackUsages": [
       {
         "Time": 1557471600,
         "Traffic": 153.064
       }
     ],
     "RequestId": "38F3D5EF-42BA-4533-81EB-AEAD068B5E02",
     "EndTime": 1557910800,
     "StartTime": 1557302400
    }
    ```


