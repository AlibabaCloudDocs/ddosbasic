# API概览 {#reference3502 .reference}

本文档汇总了BGP高防IP所有可调用的API，具体接口信息请参阅相关文档。

关于更多API资源，请访问[API Explorer](https://api.aliyun.com)。

## 实例 { .section}

|API|描述|
|[DescribeInstances](cn.zh-CN/新BGP高防IP/API 参考/实例/DescribeInstances.md#)|查询实例列表。|
|[ReleaseInstance](cn.zh-CN/新BGP高防IP/API 参考/实例/ReleaseInstance.md#)|释放实例。|
|[DescribeInstanceDetails](cn.zh-CN/新BGP高防IP/API 参考/实例/DescribeInstanceDetails.md#)|查询实例详情列表。|
|[DescribeInstanceSpecs](cn.zh-CN/新BGP高防IP/API 参考/实例/DescribeInstanceSpecs.md#)|查询实例规格列表。|
|[DescribeInstanceStatistics](cn.zh-CN/新BGP高防IP/API 参考/实例/DescribeInstanceStatistics.md#)|查询实例统计信息。|
|[DescribeElasticBandwidthSpec](cn.zh-CN/新BGP高防IP/API 参考/实例/DescribeElasticBandwidthSpec.md#)|查询弹性带宽规格。|
|[ModifyElasticBandWidth](cn.zh-CN/新BGP高防IP/API 参考/实例/ModifyElasticBandWidth.md#)|修改弹性防护带宽。|
|[ModifyInstanceRemark](cn.zh-CN/新BGP高防IP/API 参考/实例/ModifyInstanceRemark.md#)|修改实例备注信息。|

## 4层规则 { .section}

|API|描述|
|[CreateLayer4Rule](cn.zh-CN/新BGP高防IP/API 参考/四层规则/CreateLayer4Rule.md#)|创建4层转发规则。|
|[ConfigLayer4Rule](cn.zh-CN/新BGP高防IP/API 参考/四层规则/ConfigLayer4Rule.md#)|编辑4层转发规则。|
|[DeleteLayer4Rule](cn.zh-CN/新BGP高防IP/API 参考/四层规则/DeleteLayer4Rule.md#)|删除4层转发规则。|
|[ConfigLayer4RuleAttribute](cn.zh-CN/新BGP高防IP/API 参考/四层规则/ConfigLayer4RuleAttribute.md#)|配置4层转发规则属性（会话保持和DDoS防护策略）。|
|[ConfigHealthCheck](cn.zh-CN/新BGP高防IP/API 参考/四层规则/ConfigHealthCheck.md#)|配置4层/7层健康检查。|
|[DescribeLayer4Rules](cn.zh-CN/新BGP高防IP/API 参考/四层规则/DescribeLayer4Rules.md#)|查询四层转发规则列表。|
|[DescribeLayer4RuleAttributes](cn.zh-CN/新BGP高防IP/API 参考/四层规则/DescribeLayer4RuleAttributes.md#)|查询四层转发属性列表（会话保持和DDoS防护策略）。|
|[DescribeHealthCheckList](cn.zh-CN/新BGP高防IP/API 参考/四层规则/DescribeHealthCheckList.md#)|查询4层/7层健康检查列表。|
|[DescribeHealthCheckStatusList](cn.zh-CN/新BGP高防IP/API 参考/四层规则/DescribeHealthCheckStatusList.md#)|查询健康检查状态。|

## 7层规则 { .section}

|API|描述|
|[DescribeDomains](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DescribeDomains.md#)|查询7层转发规则。|
|[CreateLayer7Rule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/CreateLayer7Rule.md#)|创建7层转发规则。|
|[ConfigLayer7Rule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/ConfigLayer7Rule.md#)|编辑7层转发规则。|
|[DeleteLayer7Rule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DeleteLayer7Rule.md#)|删除7层转发规则。|
|[ConfigLayer7Cert](cn.zh-CN/新BGP高防IP/API 参考/七层规则/ConfigLayer7Cert.md#)|设置证书。|
|[ConfigLayer7BlackWhiteList](cn.zh-CN/新BGP高防IP/API 参考/七层规则/ConfigLayer7BlackWhiteList.md#)|设置7层防护黑白名单。|
|[DescribleLayer7InstanceRelations](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DescribleLayer7InstanceRelations.md#)|查询7层防护实例对应关系。|
|[DescribleCertList](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DescribleCertList.md#)|查询证书列表。|
|[EnableLayer7CC](cn.zh-CN/新BGP高防IP/API 参考/七层规则/EnableLayer7CC.md#)|启用7层CC防护。|
|[DisableLayer7CC](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DisableLayer7CC.md#)|禁用7层CC防护。|
|[EnableLayer7CCRule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/EnableLayer7CCRule.md#)|启用7层CC规则。|
|[DisableLayer7CCRule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DisableLayer7CCRule.md#)|禁用7层CC规则。|
|[AddLayer7CCRule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/AddLayer7CCRule.md#)|添加7层CC规则。|
|[ConfigLayer7CCRule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/ConfigLayer7CCRule.md#)|编辑7层CC规则。|
|[DescribeLayer7CCRules](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DescribeLayer7CCRules.md#)|查询7层CC规则。|
|[DeleteLayer7CCRule](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DeleteLayer7CCRule.md#)|删除7层CC规则。|
|[ConfigLayer7CCTemplate](cn.zh-CN/新BGP高防IP/API 参考/七层规则/ConfigLayer7CCTemplate.md#)|设置7层CC防护模板。|
|[DescribeDomainAccessMode](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DescribeDomainAccessMode.md#)|查询域名接入模式。|
|[ConfigDomainAccessMode](cn.zh-CN/新BGP高防IP/API 参考/七层规则/ConfigDomainAccessMode.md#)|设置域名接入模式。|
|[DescribeBackSourceCidr](cn.zh-CN/新BGP高防IP/API 参考/七层规则/DescribeBackSourceCidr.md#)|查询回源网段。|

## 事件任务 { .section}

|API|描述|
|[ListAsyncTask](cn.zh-CN/新BGP高防IP/API 参考/事件任务/ListAsyncTask.md#)|查询异步任务列表。|
|[CreateAsyncTask](cn.zh-CN/新BGP高防IP/API 参考/事件任务/CreateAsyncTask.md#)|创建异步任务。|
|[DeleteAsyncTask](cn.zh-CN/新BGP高防IP/API 参考/事件任务/DeleteAsyncTask.md#)|删除异步任务。|

## 图表 { .section}

|API|描述|
|[DescribeIpTraffic](cn.zh-CN/新BGP高防IP/API 参考/图表/DescribeIpTraffic.md#)|查询IP流量信息。|
|[DescribeDDoSTraffic](cn.zh-CN/新BGP高防IP/API 参考/图表/DescribeDDoSTraffic.md#)|查询DDoS攻击流量信息。|
|[DescribeDDoSEvents](cn.zh-CN/新BGP高防IP/API 参考/图表/DescribeDDoSEvents.md#)|查询DDoS攻击事件列表。|
|[DescribeDomainQps](cn.zh-CN/新BGP高防IP/API 参考/图表/DescribeDomainQps.md#)|查询域名QPS。|
|[DescribeDomainAttackEvents](cn.zh-CN/新BGP高防IP/API 参考/图表/DescribeDomainAttackEvents.md#)|查询域名攻击事件。|

## 日志 { .section}

|API|描述|
|[DescribeOpEntities](cn.zh-CN/新BGP高防IP/API 参考/日志/DescribeOpEntities.md#)|查询操作日志。|

