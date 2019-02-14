# Scenarios {#concept_92221_zh .concept}

The Internet is interconnected by local network operators to achieve global access. However, due to different policies of network operators in different regions, the actual network access and communication is different. Therefore, you have to use an appropriate DDoS protection solutions according to your business scenarios.

**Note:** 

Because of the current routing and interconnection strategies of network operators, if only the Anti-DDoS Premium service is enabled, users in mainland China have to access Anti-DDoS Premium resources deployed outside the mainland China, and the quality of the network link is affected.

The average network delay time reaches 300 ms, and the network link is affected by international link congestion resulting in intermittent packet loss. Therefore, we strongly recommend that you deploy servers in mainland China to serve users in mainland China, use Anti-DDoS Pro service to mitigate DDoS attacks, and complete website registration and other compliance procedures to comply with relevant Chinese laws and regulations.

For servers that are deployed outside mainland China, see the following three scenarios:

## Scenario 1: The Business Server is deployed in non-mainland China and mainly serves users from non-Mainland China {#section_ksh_mtw_fgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79665/154780947435114_en-US.png)

Purchase Anti-DDoS Premium, and add your business to the Anti-DDoS Premium instance for DDoS protection according to [Enable Anti-DDoS Premium](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Enable Anti-DDoS Premium.md#).

## Scenario 2: Servers deployed outside mainland China, while serving users in mainland China { .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79665/154780947435116_en-US.png)

Solutions:

-   Solution A

    If your business has high requirements on network quality \(for example, gaming servers\), we recommend that you migrate your servers to the mainland China region that your major users located in, and purchase [the Anti-DDoS Pro service](../../../../../reseller.en-US/Anti-DDoS Pro Service/Product Introduction/What is Anti-DDoS Pro.md#)to mitigate DDoS attacks.

-   Solution B

    If your business servers are not planned to be migrated to mainland China, contact our sales or submit a ticket to purchase the Mainland China Acceleration \(MCA\) plan of Anti-DDoS Premium. Then, our technical support helps you to deploy the Anti-DDoS Smart Switch solution to guarantee smooth access for users in mainland China by utilizing the acceleration lines when no DDoS attack happens. For more information about MCA, view [Configure Anti-DDoS Premium MCA](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Configure Anti-DDoS Premium MCA.md#).


## Scenario 3: Servers deployed outside mainland China, while serving users both in and outside mainland China { .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79665/154780947435130_en-US.png)

Solutions:

-   Solution A

    We recommend that you deploy business servers separately for the two regions, using servers deployed in mainland China to serve users in mainland China and using servers deployed outside mainland China to serve users outside mainland China. Meanwhile, purchase [the Anti-DDoS Pro service](../../../../../reseller.en-US/Anti-DDoS Pro Service/Product Introduction/What is Anti-DDoS Pro.md#) and the Anti-DDoS Premium service for businesses in and outside mainland China to mitigate DDoS attacks.

-   Solution B

    If you do not plan to deploy business servers in mainland China, contact our sales or submit a ticket to purchase the Mainland China Acceleration \(MCA\) plan of Anti-DDoS Premium. Then, our technical support helps you to deploy the Anti-DDoS Smart Switch solution to guarantee smooth access for users in mainland China by utilizing the acceleration lines when no DDoS attack happens. For more information about MCA, view [Configure Anti-DDoS Premium MCA](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Configure Anti-DDoS Premium MCA.md#).


