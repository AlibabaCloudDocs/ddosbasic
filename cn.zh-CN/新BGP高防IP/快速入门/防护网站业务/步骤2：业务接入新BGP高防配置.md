# 步骤2：业务接入新BGP高防配置 {#task_221012 .task}

本文以阿里云云解析DNS为例，介绍如何在添加新BGP高防网站配置后，手动修改防护域名的DNS解析A记录，将您的网站业务切换至已配置的新BGP高防IP。

修改DNS解析前，您需要完成以下任务：

-   添加网站配置。具体操作请参考[步骤1：添加网站配置](cn.zh-CN/新BGP高防IP/快速入门/防护网站业务/步骤1：添加网站配置.md#)。
-   如果您网站的源站服务器已经部署其他防火墙，请关闭防火墙或将新BGP高防IP的所有回源地址加入防火墙的白名单。 具体操作请参考[放行新BGP高防回源IP](cn.zh-CN/新BGP高防IP/用户指南/放行新BGP高防回源IP.md#)。

    将网站访问流量切换至新BGP高防IP后，您网站的正常访问流量经过所配置的新BGP高防IP实例后，将通过这些回源IP地址转发给源站服务器。因此，如果新BGP高防IP的回源地址未被加入防火墙的白名单中，访问流量可能被防火墙错误拦截，导致网站无法访问。

-   验证转发配置。强烈建议您在切换网站访问流量前，验证并确认新BGP高防IP实例转发配置已经生效。具体操作请参考[网站配置生效测试](../../../../cn.zh-CN/DDoS高防IP/快速入门/防护网站业务/步骤3：验证配置生效.md#)。

以下操作描述建立在您的域名DNS托管在[阿里云云解析DNS](https://wanwang.aliyun.com/domain/dns)。若您使用其他DNS服务商的域名解析服务，请登录服务商系统，将防护域名的解析A记录值更新为关联高防IP。

**说明：** 云解析DNS是阿里云提供的域名解析服务，支持免费的公共DNS服务和付费版增值服务。如果您的域名已开通付费版云解析DNS服务，我们推荐您使用NS接入（即自动修改DNS）的方式接入新BGP高防。具体操作请参考[NS接入](cn.zh-CN/新BGP高防IP/用户指南/NS接入.md#)。

假设在步骤1添加网站配置中，您添加的防护域名为`ddoscoo.doctest.top`；以下操作示例描述了在云解析DNS控制台修改/新增域名解析A记录的具体步骤。

1.  登录[阿里云云解析DNS控制台](https://dns.console.aliyun.com)[阿里云云解析DNS控制台](https://partners-dns.console.aliyun.com)。
2.  在域名解析页面，定位到要操作的域名（本示例中为`doctest.top`），单击其操作列下的**解析设置**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/155771812545866_zh-CN.png)


3.  在解析设置页面，定位到要修改的解析A记录（本示例中，即主机记录为**ddoscoo**的A记录），单击其操作列下的**修改**。 

    **说明：** 如果要操作的解析A记录不在记录列表中，您可以单击**添加记录**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/155771812545867_zh-CN.png)

4.  在修改记录（或添加记录）对话框，将**记录值**修改为域名的关联高防IP。 

    **说明：** 当您在新BGP高防IP控制台成功添加域名配置后，新BGP高防为域名分配一个关联高防IP。您可以在[新BGP高防IP控制台](https://yundunnext.console.aliyun.com/?p=ddoscoo)[新BGP高防IP控制台](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo)，**管理** \> **网站配置**页面，查看已添加域名的关联高防IP。具体请参考[步骤1：添加网站配置](cn.zh-CN/新BGP高防IP/快速入门/防护网站业务/步骤1：添加网站配置.md#)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/155771812545904_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/155771812545868_zh-CN.png)

5.  单击**确定**，等待修改后的解析设置生效。

[步骤3：设置DDoS防护策略](cn.zh-CN/新BGP高防IP/快速入门/防护网站业务/步骤3：设置DDoS防护策略.md#)

