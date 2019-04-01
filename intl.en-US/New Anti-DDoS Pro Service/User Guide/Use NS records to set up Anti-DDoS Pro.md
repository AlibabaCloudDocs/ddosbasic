# Use NS records to set up Anti-DDoS Pro {#task893 .task}

To set up Anti-DDoS Pro to protect your business, you must modify the DNS records of your domain to forward incoming traffic to your Anti-DDoS Pro instances. If your domain is managed by Alibaba Cloud DNS, you can enable NS Mode Access to automatically modify DNS records. Otherwise, you can only manually modify DNS records through your DNS provider. This topic describes how to enable NS Mode Access in the Anti-DDoS Pro console.

Your domain is managed under a paid version of Alibaba Cloud DNS. Otherwise, you cannot enable NS Mode Access. We recommend that you [activate a paid version of Alibaba Cloud DNS](https://wanwang.aliyun.com/domain/dns).

NS Records are nameserver records. You can use NS records to specify which DNS server is used to resolve your domain name.

Anti-DDoS Pro supports two modes when you enable NS Mode Access: Anti-DDoS Pro and Back-to-Origin.

-   The Anti-DDoS Pro mode automatically modifies DNS records to forward incoming traffic to your Anti-DDoS Pro instances.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411453036781_en-US.png)

-   The Back-to-Origin mode automatically synchronizes DNS records between Anti-DDoS Pro instances and Alibaba Cloud DNS. Incoming traffic is still directed to your origin server.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411453036787_en-US.png)


We recommend that you use the following steps to enable NS Mode Access. If you cannot enable NS Mode Access, you must manually change the DNS records of your domain through your DNS provider.

To forward incoming traffic to Anti-DDoS Pro, you need to change A record values to the IP addresses of your Anti-DDoS Pro instances.

1.  Log on to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo#/report). 
2.  In the left-side navigation pane, choose **Management** \> **Websites**. 
3.  Select your domain and click **Configure DNS Settings**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411453036794_en-US.png)

4.  Enable **NS Mode Access**. 

    **Note:** If you are not using a paid version of Alibaba Cloud DNS, an error message appears when you enable NS Mode Access.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79687/155411453036801_en-US.png)

5.  Select the Anti-DDoS Pro or Back-to-Origin mode based on your needs. 
    -   When the Anti-DDoS Pro mode is selected, Anti-DDoS Pro automatically modifies the DNS records at Alibaba Cloud DNS so that incoming traffic is directed to your Anti-DDoS Pro instances.
    -   When the Back-to-Origin mode is selected, DNS records are automatically synchronized between Anti-DDoS Pro and Alibaba Cloud DNS. Incoming traffic is still directed to your origin server.
6.  After the configuration is complete, you can use DNS testing tools to verify whether the configuration works as expected. 

