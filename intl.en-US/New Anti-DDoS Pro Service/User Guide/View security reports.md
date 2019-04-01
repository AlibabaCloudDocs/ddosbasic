# View security reports {#task612 .task}

After you set up Anti-DDoS Pro to protect your business, you can find statistics about your traffic and protection status in the Anti-DDoS Pro console.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo). 
2.  In the left-side navigation pane, choose **Security Reports**. 
    -   On the Service page, select an Anti-DDoS Pro instance and port, and specify a time range to view the inbound and outbound bandwidth, trends, and connections to your service.

        **Note:** You can query traffic and connection data for up to 30 days.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79697/155411471436934_en-US.png)

        You can drag the slider to quickly change time ranges.

    -   On the Anti-DDoS Protection page, select an Anti-DDoS Pro instance and specify a time range to view the traffic trends to your site and information about DDoS attacks.

        **Note:** You can query traffic data and DDoS attacks for up to 30 days.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79697/155411471436935_en-US.png)

        **Note:** Anti-DDoS Pro automatically filters out abnormal packets, for example, SYN packets, packets with invalid flags, and invalid TCP packets. This helps save server resources. Incoming traffic is scrubbed when abnormal packets are detected. This is why scrubbed traffic appears in the traffic chart when the traffic bandwidth to your server does not reach the scrubbing threshold.

    -   On the HTTP Flood Protection page, select a domain and specify a time range to view the trend of requests and information about HTTP flood attacks.

        **Note:** You can query request data and HTTP flood attacks for up to 30 days.


