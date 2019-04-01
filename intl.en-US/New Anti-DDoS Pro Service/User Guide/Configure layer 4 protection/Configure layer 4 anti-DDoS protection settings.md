# Configure layer 4 anti-DDoS protection settings {#task1011 .task}

Anti-DDoS Pro supports protection against layer 4 DDoS attacks and provides multiple protection settings to safeguard the security of your business.

Anti-DDoS Pro provides protection against DDoS attacks based on IPs and ports when no domain names are provided. You can set limits on parameters such as the request rate, and packet length to mitigate DDoS attacks.

Anti-DDoS Pro supports the following anti-DDoS protection settings for you to choose from:

**Note:** The **New Connection Speed Limits for Source IP** setting supports the automatic protection mode. If the automatic protection mode is selected, Anti-DDoS Pro dynamically calculates the limit on the number of new connections per second from a single source IP. If the manual mode is selected, you need to manually specify the limit on the new connection rate.

|Settings|Description|
|--------|-----------|
|False Sources|Detects and blocks false source IPs. This setting is only applicable to TCP rules.|
|Null Session Connections|Detects and blocks null session connections. This setting is only applicable to TCP rules.|
|New Connection Speed Limits for Source IP|The maximum number of new connections per second from a single source IP. All new connections exceeding the limit are discarded. The actual limit on the new connection rate may be slightly different because the protection servers are deployed in clusters.|
|Concurrent Connection Speed Limits for Source IP|The maximum number of concurrent connections from a single source IP. All connections exceeding the limit are discarded.|
|New Connection Speed Limits for Destination IP|The maximum number of new connections per second to a single destination IP and port. All new connections exceeding the limit are discarded. The actual limit on the new connection rate may be slightly different because the protection servers are deployed in clusters.|
|Concurrent Connection Speed Limits for Destination IP|The maximum number of concurrent connections to a single destination IP and port. All connections exceeding the limit are discarded.|
|Packet Length Filtering|The limit on the payload size of a packet. Unit: byte. All packets exceeding the size limit are discarded.|

You can configure anti-DDoS protection settings for specific ports on specific IP addresses.

**Note:** Anti-DDoS protection settings take effect for single ports.

1.  Log on to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo#/report). 
2.  In the left-side navigation pane, choose **Management** \> **Port Settings**, select an Anti-DDoS Pro instance and forwarding rule, and click **Configure** under the Anti-DDoS Protection Policy column. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79689/155411455636886_en-US.png)

3.  In the **Anti-DDoS Protection Policy** dialog box, configure Anti-DDoS protection settings for the selected IP and port. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79689/155411455636891_en-US.png)


