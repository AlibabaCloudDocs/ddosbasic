# DescribleLayer7InstanceRelations {#reference1579 .reference}

调用DescribleLayer7InstanceRelations查询7层防护实例和EIP的对应关系。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|DomainList|\[\]String|是|要查询的域名列表。|

## 返回参数 {#section_rqk_pxz_jgb .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Layer7InstanceRelation|\[\]Layer7InstanceRelation|7层实例的防护关系列表。具体结构描述见[Layer7InstanceRelation](#)。|

|名称|类型|描述|
|--|--|--|
|Domain|String|域名。|
|InstanceDetails|\[\]InstanceDetail|实例信息列表。具体结构描述见[InstanceDetail](#)。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|Line|String|防护线路。例如，coop-line-001。|
|EipList|\[\]String|绑定的EIP列表。例如，\["1.1.1.1"\]。|

## 示例 { .section}

**请求示例** 

```
{
  "DomainList": ["1.aliyun.com","2.aliyun.com"]
}
				
```

**返回示例** 

```
{
    "Layer7InstanceRelations":[
        {
            "Domain":"1.aliyun.com",
            "InstanceDetails":[
                {
                    "EipList":[
                        "203.x.x.0",
                        "203.x.x.1"
                    ],
                    "InstanceId":"xxxxxx"
                },
                {
                    "EipList":[
                        "203.x.x.0",
                        "203.x.x.1"
                    ],
                    "InstanceId":"xxxxxx"
                }
            ]
        }
    ]
}
				
```

