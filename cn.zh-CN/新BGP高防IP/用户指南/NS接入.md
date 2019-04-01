# NS接入 {#task893 .task}

在接入新BGP高防时，您首先要完成网站配置，然后必须通过修改域名DNS，将业务流量牵引到新BGP高防实例。DNS配置支持NS接入（自动修改DNS）和手动修改两种方式。本文介绍了使用NS接入的操作方法。

您的域名使用收费版阿里云解析DNS提供的DNS服务。如果您未开通阿里云解析DNS付费版本，则无法使用NS方式。建议先[开通阿里云解析DNS付费版服务](https://wanwang.aliyun.com/domain/dns)，再进行配置。

Name Server（NS）记录是指域名服务器记录，用于指定该域名由哪个DNS服务器来进行解析。

使用NS接入时，支持两种接入模式：高防和回源。

-   高防模式：将自动修改DNS记录，实现将业务流量牵引到新BGP高防上。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411452836781_zh-CN.png)

-   回源模式：将自动修改DNS记录，实现将业务流量指回源站。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411452836787_zh-CN.png)


推荐您参照本文操作步骤使用NS方式接入，方便操作。如果因特殊情况无法使用NS方式（如不具备阿里云解析DNS服务），请通过手动方式来修改DNS，将待防护业务流量牵引到新BGP高防实例。

手动修改DNS需要您通过域名的DNS服务商或DNS服务页面手动修改DNS，更新解析A记录的值为新BGP高防IP地址，从而将业务流量牵引到新BGP高防实例上。

1.  登录[新BGP高防云盾管理控制台](https://yundunnext.console.aliyun.com/?p=ddoscoo#/report)。 
2.  定位到**管理** \> **网站配置**页面。 
3.  选择要操作的域名，单击**DNS设置**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411452836794_zh-CN.png)

4.  开启**NS方式接入**。 

    **说明：** 如果当前不具有阿里云解析DNS收费版服务，将提示无法使用NS方式；如果已具有阿里云解析DNS收费版服务，开关将正常开启。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411452936801_zh-CN.png)

5.  根据需要选择接入模式：高防、回源。 
    -   选择高防模式，新BGP控制台将自动同步阿里云解析DNS服务，将该域名的解析目标指向新BGP高防。
    -   选择回源模式，新BGP控制台将自动同步阿里云解析DNS服务，将该域名的解析目标指向源站。
6.  完成配置后，您可以通过第三方DNS测试平台来检测该域名当前最新解析结果是否符合预期。 

