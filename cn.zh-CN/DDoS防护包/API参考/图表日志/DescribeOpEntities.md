# DescribeOpEntities {#reference_265087 .reference}

调用DescribeOpEntities接口查询用户的操作日志。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeOpEntities。|
|CurrentPage|Integer|是|列表的页码，默认值为1。|
|EndTime|Long|是|查询结束时间，秒级时间戳。|
|PageSize|Integer|是|分页查询时每页的行数，最大值为50，默认值为10。|
|StartTime|Long|是|查询开始时间，秒级时间戳。|
|OrderBy|String|否|排序字段，取值：opdate（操作时间）。|
|OrderDir|String|否|排序方向，取值： -   ASC：正序
-   DESC：倒序

 |
|InstanceId|String|否|要查询的防护包实例ID。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|TotalCount|Integer|返回结果的数量。|
|OpEntities|Array|操作日志信息。|
|└EntityObject|String|操作对象，即防护包实例。|
|└EntityType|Integer|操作对象类型，取值：1（实例）。|
|└GmtCreate|Long|日志创建时间。|
|└OpAccount|String|操作账号，取值：system（系统）。|
|└OpAction|Integer|操作类型，取值： -   3：添加IP
-   4：解绑IP
-   5：实例降级
-   6：解除黑洞
-   7：重置解除黑洞次数
-   8：恢复弹性

 |
|└OpDesc|String|操作说明。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeOpEntities
&InstanceId=ddosbgp-cn-x1
&StartTime=1555314714011
&EndTime=1557906714012
&CurrentPage=1
&PageSize=10
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeOpEntitiesResponse>
       <TotalCount>1</TotalCount>
       <OpEntities>
           <OpEntity>
               <OpAccount>system</OpAccount>
               <OpDesc>{"entity":{"baseBandwidth":20,"elasticBandwidth":101}}</OpDesc>
               <EntityObject>ddosbgp-cn-o4013qftb006</EntityObject>
               <EntityType>1</EntityType>
               <GmtCreate>1557821673000</GmtCreate>
               <OpAction>8</OpAction>
           </OpEntity>
       </OpEntities>
       <RequestId>6B60EC77-2F66-4EBD-879D-4F26B15CB0B2</RequestId>
    </DescribeOpEntitiesResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "TotalCount": 1,
     "OpEntities": [
       {
         "OpAccount": "system",
         "OpDesc": "{\"entity\":{\"baseBandwidth\":20,\"elasticBandwidth\":101}}",
         "EntityObject": "ddosbgp-cn-o4013qftb006",
         "EntityType": 1,
         "GmtCreate": 1557821673000,
         "OpAction": 8
       }
     ],
     "RequestId": "52C8ECB0-0B1A-4E66-A31C-B6A855120E82"
    }
    ```


