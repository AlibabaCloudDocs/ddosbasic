# DescribeExcpetionCount {#reference_265084 .reference}

调用DescribeExcpetionCount接口查询防护包异常信息。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeExcpetionCount。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|ExceptionIpCount|Integer|异常IP的数量，如被防护的ECS IP、SLB IP等。|
|ExpireTimeCount|Integer|7天内即将到期的实例数量。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeExcpetionCount
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeExcpetionCountResponse>
       <ExpireTimeCount>1</ExpireTimeCount>
       <RequestId>58609615-FCF9-41DF-8B25-0D5C8DAB92BA</RequestId>
       <ExceptionIpCount>0</ExceptionIpCount>
    </DescribeExcpetionCountResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "ExpireTimeCount": 1,
     "RequestId": "A3EEE55F-3B9F-4765-8C03-1A1A904F3451",
     "ExceptionIpCount": 0
    }
    ```


