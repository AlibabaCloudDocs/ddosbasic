# ModifyRemark {#reference_265095 .reference}

调用ModifyRemark接口修改DDoS防护包的备注。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：ModifyRemark。|
|InstanceId|String|是|要操作的防护包实例ID。|
|Remark|String|是|要添加的备注内容。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=ModifyRemark
&InstanceId=ddosbgp-cn-xxx
&Remark=test
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <ModifyRemarkResponse>
        <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
    </ModifyRemarkResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216"
    }
    ```


