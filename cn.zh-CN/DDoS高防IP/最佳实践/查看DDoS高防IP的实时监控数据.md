# 查看DDoS高防IP的实时监控数据 {#task_lyc_4by_dgb .task}

该章节介绍如何在云服务控制台上查看DDoS高防IP的实时监控数据。通过查看DDoS高防IP的实时监控数据，帮助您全面了解业务的DDoS高防IP的防护情况。

DDoS高防IP的实时监控数据包括以下：

|监控项|维度|单位|
|---|--|--|
|高防IP出流量|实例维度、IP维度|bit/s|
|高防IP入流量|实例维度、IP维度|bit/s|
|高防IP回源带宽|实例维度、IP维度|bit/s|
|高防IP攻击流量|实例维度、IP维度|bit/s|
|高防IP活跃并发连接|实例维度、IP维度|个|
|高防IP非活跃并发连接|实例维度、IP维度|个|
|高防IP新建连接|实例维度、IP维度|个|

**说明：** 高防IP回源带宽是指通过高防清洗后回源到源站服务器的干净业务流量带宽。

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)，定位到**云服务监控** \> **DDoS高防IP**。 
2.  在**实例列表**中，单击高防实例名称或**操作**栏中的**监控图表**，即可进入DDoS高防IP的实例监控图表页面。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/80604/154514448734491_zh-CN.png) 

3.  单击页面上方的**时间范围**快速选择按钮或精确选择时间段，查看各项监控项数据。 监控数据最长支持查看连续30天的监控数据。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/80604/154514448734492_zh-CN.png) 

4.  单击监控图右上角的放大按钮，可查看监控大图。 

