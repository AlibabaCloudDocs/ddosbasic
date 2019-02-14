# CreateAsyncTask {#reference1005 .reference}

调用CreateAsyncTask创建异步任务。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|TaskType|Integer|是|任务类型，取值：-   1：4层转发规则批量导出任务
-   2：7层防护规则批量导出任务
-   3：会话&健康检查配置导出任务
-   4：DDoS防护策略导出任务

|
|TaskParams|String|是|任务参数，一组json字符串，根据TaskType不同有所区别。-   TaskType为1时，传入需要导出规则的新BGP高防实例Id。例如，\{“instanceId”: “ddoscoo-cn-XXXXX”\}
-   TaskType为2时，传入一个空对象的字符串即可。例如，\{\}
-   TaskType为3时，传入需要导出规则的新BGP高防实例Id。例如，\{“instanceId”: “ddoscoo-cn-XXXXX”\}
-   TaskType为4时，传入需要导出规则的新BGP高防实例Id。例如，\{“instanceId”: “ddoscoo-cn-XXXXX”\}

|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "TaskType": 1,
  "TaskParams": "{}" // 四层任务：{"instanceId": "ddoscoo-woieuroi234"}，七层任务：{}，会话&健康检查任务：{"instanceId": "xxxxxxxxxx"}，DDoS防护策略任务：{"instanceId": "xxxxxxxxxx"}
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

