# API概览 {#reference_266557 .reference}

本文汇总了DDoS防护包服务的所有可调用API，具体接口信息请参见相关文档。

## 防护设置相关接口 {#section_z1i_qiz_f4m .section}

|接口|描述|
|--|--|
|[AddIp](cn.zh-CN/DDoS防护包/API参考/防护/AddIp.md#)|为DDoS防护包添加防护对象IP。|
|[DeleteIp](cn.zh-CN/DDoS防护包/API参考/防护/DeleteIp.md#)|将被防护IP从防护包中移除，取消防护。|
|[DeleteBlackhole](cn.zh-CN/DDoS防护包/API参考/防护/DeleteBlackhole.md#)|为被防护IP解除黑洞状态。|

## 防护包实例相关接口 {#section_uv8_eyc_utw .section}

|接口|描述|
|--|--|
|[DescribeRegions](cn.zh-CN/DDoS防护包/API参考/实例/DescribeRegions.md#)|查看DDoS防护包服务支持的地域信息。|
|[DescribeInstanceList](cn.zh-CN/DDoS防护包/API参考/实例/DescribeInstanceList.md#)|查询防护包实例的详细信息。|
|[DescribeInstanceSpecs](cn.zh-CN/DDoS防护包/API参考/实例/DescribeInstanceSpecs.md#)|查询防护包实例的规格信息。|
|[DescribeExcpetionCount](cn.zh-CN/DDoS防护包/API参考/实例/DescribeExcpetionCount.md#)|查询异常防护包实例的信息。|
|[DescribePackIpList](cn.zh-CN/DDoS防护包/API参考/实例/DescribePackIpList.md#)|查询防护包实例的防护IP列表信息。|
|[ModifyRemark](cn.zh-CN/DDoS防护包/API参考/实例/ModifyRemark.md#)|修改DDoS防护包的备注。|
|[CheckGrant](cn.zh-CN/DDoS防护包/API参考/实例/CheckGrant.md#)|检查防护包服务的授权状态，即是否授权防护包查询您的ECS服务器信息。|

## 抗D流量包相关接口 {#section_jbb_l0h_q01 .section}

|接口|描述|
|--|--|
|[DescribeResourcePackInstances](cn.zh-CN/DDoS防护包/API参考/流量包/DescribeResourcePackInstances.md#)|查询抗D流量包的详细信息。|
|[DescribeResourcePackStatistics](cn.zh-CN/DDoS防护包/API参考/流量包/DescribeResourcePackStatistics.md#)|查询抗D流量包的统计信息。|
|[DescribeResourcePackUsage](cn.zh-CN/DDoS防护包/API参考/流量包/DescribeResourcePackUsage.md#)|查询抗D流量包的使用明细。|
|[DescribePackPaidTraffic](cn.zh-CN/DDoS防护包/API参考/流量包/DescribePackPaidTraffic.md#)|查询付费流量明细。|

## 图表日志相关接口 {#section_csr_i4z_wct .section}

|接口|描述|
|--|--|
|[DescribeDdosEvent](cn.zh-CN/DDoS防护包/API参考/图表日志/DescribeDdosEvent.md#)|查询指定防护包上的DDoS事件。|
|[DescribeOpEntities](cn.zh-CN/DDoS防护包/API参考/图表日志/DescribeOpEntities.md#)|查询用户的操作日志。|

