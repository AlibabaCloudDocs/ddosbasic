# AddLayer7CCRule {#reference1206 .reference}

调用AddLayer7CCRule为指定域名添加7层CC规则。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要操作的域名。|
|Name|String|是|CC自定义规则名。|
|Act|String|是|规则触发后的操作，取值：-   close：封禁
-   captcha：人机识别

|
|Count|Integer|是|访问次数，与Interval结和使用。当同一个IP在Interval指定的间隔时间内连续访问Count中指定的访问次数，则触发规则。|
|Interval|Integer|是|间隔时间，与Count结和使用。当同一个IP在Interval指定的间隔时间内连续访问Count中指定的访问次数，则触发规则。|
|Mode|String|是|URI匹配模式，取值：-   match：完全匹配。访问请求的URI与指定的Uri完全相同，才计入访问次数。
-   prefix：前缀匹配。访问请求的URI包含指定的Uri，则计入访问次数。

|
|Ttl|Integer|是|若规则触发后动作指定为封禁，设置封禁时间。|
|Uri|String|是|被防护的URI。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "Domain": "www.alibaba.com",
  "Name":"XXXX",
  "Act":"close",
  "Count":11,
  "Interval":5,
  "Mode":"match",
  "Ttl":1,
  "Uri":"/a/b/c.htm"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

