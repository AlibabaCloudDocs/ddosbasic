# Add a non-website business to Anti-DDoS Premium for protection {#task1142 .task}

After purchasing an Anti-DDoS Premium instance, you can add your non-website business, such as client game, mobile game or APP, to the instance for DDoS protection.

**Note:** Compared with website protection, non-website protection only provides layer 4 port protection, such as SYN, ACK, ICMP, and UDP floods. It cannot mitigate layer 7 attacks, such as HTTP floods, and web application attacks, such as SQL injection and XSS.

**Note:** If you want to add a website domain to Anti-DDoS Premium, see [Add website to Anti-DDoS Premium for protection](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Add website to Anti-DDoS Premium for protection.md#).

1.  Log on to the [Anti-DDoS Premium Service console](https://partners-intl.console.aliyun.com/#/ddosdip). 
2.  Go to **Provisioning** \> **Non-Website** page, select an Anti-DDoS Premium instance, and click **Add Rule**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79671/154780973935261_en-US.png) 

3.  On the Add Rule page, configure the following rule, and click **Confirm**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79671/154780973935264_en-US.png) 

    |Parameter|Description|Note|
    |---------|-----------|----|
    |Protocol|Protocols supported by the website.|The TCP and UDP protocols are supported.|
    |Service Port|Port that used by the Anti-DDoS Premium instance to provide public service for the business. We recommend that you set the service port to the same port as the origin server port.|Any port from 1 to 65535 is supported.|
    |The port of the origin.|Origin server port that provides service for the business.|Any port from 1 to 65535 is supported.|
    |Source station IP|IP address of the origin server.|You can set up to 20 origin server IPs. If multiple origin IPs are set, the system forwards traffic to these IPs by using the Round Robin mode to realize load balancing.|

4.  After you verify that the Anti-DDoS Premium forwarding rule works as expected, switch your business traffic to the Dedicated IP of the Anti-DDoS Premium instance. 

    **Note:** Log on to the [Anti-DDoS Premium Service console](https://partners-intl.console.aliyun.com/#/ddosdip). On the Instance Listpagepage, you can find the Dedicated IP of the Anti-DDoS Premium instance.

    -   If your business uses IP to access the origin server, change the business IP to the Dedicated IP of Anti-DDoS Premium.
    -   If your business also uses a domain to access the origin server \(For example, you set the “aliyundemo.com” domain as the server address in the client program\), go the DNS service provider of the domain and change the A record to point to the Dedicated IP of Anti-DDoS Premium.

