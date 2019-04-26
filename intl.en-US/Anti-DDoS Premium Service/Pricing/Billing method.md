# Billing method {#concept_86324_zh .concept}

Anti-DDoS Premium offers **Insurance Plan** and **Unlimited Plan**.

## Advanced mitigation feature of Anti-DDoS Premium {#section_jdh_prd_ggb .section}

Integrating all mitigation capacities of Alibaba Cloud Anti-DDoS scrubbing centers around the world, Anti-DDoS Premium defends against all DDoS attacks to secure your business.

In most cases, the chances of being attacked decrease significantly after you have successfully defended against DDoS attacks using the Anti-DDoS service. Typically, attackers launch DDoS attacks to cause financial losses to your business. Due to the cost of launching attacks, if the attackers fail to achieve this purpose, they will stop launching DDoS attack. Therefore, the advanced mitigation of Anti-DDoS Premium provides unlimited mitigation capacities and can integrate all mitigation capacities of Alibaba Cloud Anti-DDoS scrubbing centers around the world to secure your business.

**Note:** If the attacks against your business impact the infrastructure of Alibaba Cloud Anti-DDoS scrubbing centers, Alibaba Cloud has the right to control the traffic. Once the traffic control is triggered on your Anti-DDoS Premium instance, your protected business may be affected. The traffic control measures include but are not limited to black hole routing and limitations to the access traffic.

## Plans of Anti-DDoS Premium {#section_nk1_y4d_ggb .section}

-   **Insurance Plan** 

    Each month, Anti-DDoS Premium Insurance Plan offers two advanced mitigations by default, featuring unlimited mitigation capabilities. This protects your businesses against DDoS attacks with full capacity within 24 hours after an attack has been detected, and consumes one advanced mitigation. The number of advanced mitigations is reset to two at the beginning of every month during the service period.

    **Note:** To purchase more advanced mitigations, see [Global advanced mitigation](reseller.en-US/Anti-DDoS Premium Service/Pricing/Global advanced mitigation.md#).

    For example, a protected IP suffers DDoS attacks at 11:20:00 \(UTC+8\), September 12, and an advanced mitigation is triggered. Within 24 hours, Anti-DDoS Premium provides unlimited mitigation capacities for this IP. The protected IP suffers another DDoS attack at 18:50:00 \(UTC+8\), September 13, and an advanced mitigation is triggered again. 24 hours later, the advanced mitigation stops and the two advanced mitigation of the Anti-DDoS Premium Insurance Plan instance in September are exhausted. The number of advanced mitigations is automatically reset to two at the beginning of the following month, October 1.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79667/155626986935184_en-US.png)

    Insurance Plan is a basic solution of Anti-DDoS Premium and applies to users who are less vulnerable to attacks.

    **Note:** Only when the DDoS attack against your business exceeds a specific threshold, namely the basic mitigation threshold, will the advanced mitigation of Anti-DDoS Premium be enabled.

-   **Unlimited Plan** 

    Anti-DDoS Premium Unlimited Plan provides unlimited advanced mitigation capabilities for your business. After you purchase the Unlimited Plan instances, Anti-DDoS Premium provides unlimited mitigation to protect your business against all DDoS attacks.


## Pricing details of Anti-DDoS Premium { .section}

The pricing details of Anti-DDoS Premium instances are shown in the following table.

|Plan|Business bandwidth|Advanced mitigation|Price \(USD/month\)|
|----|------------------|-------------------|-------------------|
|Insurance|100 Mbps|2/month|2,630|
|Unlimited|Unlimited|11,560|
|Insurance|150 Mbps|2/month|3,420|
|Unlimited|Unlimited|12,610|
|Insurance|200 Mbps|2/month|4,210|
|Unlimited|Unlimited|13,660|
|Insurance|250 Mbps|2/month|5,000|
|Unlimited|Unlimited|14,720|
|Insurance|300 Mbps|2/month|5,570|
|Unlimited|Unlimited|15,770|

**Note:** If you need a higher Clean bandwidth, contact Alibaba Cloud technical support.

**Note:** Clean bandwidth refers to the maximum normal clean bandwidth that can be processed by Anti-DDoS Premium instances when your business is not under attack. Make sure that the Clean bandwidth of the instance is greater than the peak value of the inbound or outbound traffic of all services connected to the Anti-DDoS Premium instances. For more information about the Clean bandwidth, see [How to select a Clean bandwidth specification](#section_rkf_vqf_4gb).

If the actual traffic volume exceeds the maximum Clean bandwidth, your business may be subject to traffic restrictions or random packet losses, and your normal business may be unavailable, slowed, or delayed for a certain period of time.

Anti-DDoS Premium instances provide the following business specifications by default:

**Note:** If you need to expand the default business specifications based on actual needs, you can upgrade the instance or expand the corresponding specifications when purchasing the instance.

|Business specifications|Descriptions|Default values|Price \(USD/month\)|
|-----------------------|------------|--------------|-------------------|
|Number of protected ports|The number of TCP/UDP ports that can be protected by the instance.|5|Every 5 ports: 150 USD/month|
|Number of protected domain names|The number of HTTP/HTTPS domain names that can be protected by the instance.|10 **Note:** Contains only one top-level domain and the subdomains or wildcard domains of this top-level domain.

 |Every 10 domain names: 150 USD/month **Note:** Every 10 protected domain names contain only one top-level domain and the subdomains or wildcard domains of this top-level domain.

 |
|Clean QPS|The maximum concurrent HTTP/HTTPS requests per second supported when the system is not under attack.| -   Insurance Plan: 500 QPS
-   Unlimited Plan: 1,000 QPS

 |Every 100 QPS: 150 USD/month|

## More information {#section_rkf_vqf_4gb .section}

**How to select a Clean bandwidth specification**

You can select an appropriate Clean bandwidth specification based on the daily inbound and outbound traffic peaks of all businesses that have or will be connected to the Anti-DDoS Premium instance. Make sure that the Clean bandwidth of the instance is greater than the peak value of the inbound and outbound traffic of all businesses.

**Note:** Typically, the outbound traffic is greater than the inbound traffic.

You can evaluate your business traffic by using ECS traffic statistics or other monitoring tools on your origin server.

**Note:** The traffic here indicates the normal business traffic.

For example, you connect all access traffic of your external business to an Anti-DDoS Premium instance to secure your business. Anti-DDoS Premium will reroute the normal access traffic to the origin server when the business is normally accessed and without being attacked. When the business is attacked, Anti-DDoS Premium filters and blocks the malicious traffic, and only reroutes the normal traffic to the origin server. Therefore, the inbound and outbound traffic you view in the ECS console is normal traffic. If your business is deployed on multiple origin servers, you need to calculate the total traffic of all origin servers.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79667/155626986938045_en-US.png)

Assume that you need to connect the businesses of three websites to an Anti-DDoS Premium instance, the normal outbound traffic peak for each business does not exceed 50 Mbps, and the total business traffic does not exceed 150 Mbps. In this case, you only need to ensure that the maximum bandwidth of the purchased instance is greater than 150 Mbps.

**Domain name specifications**

Anti-DDoS Premium instances support adding 10 domain names for protection by default, including one top-level domain and the subdomains or wildcard domains of the top-level domain.

Taking `abc.com` for example, you can add the top-level domain itself and a maximum of nine subdomains, such as `www.abc.com`, `*.abc.com`, `mail.abc.com`, `user.pay.abc.com`, and `x.y.z.abc.com`. Each domain name that you have added, including the top-level domain `abc.com` counts in the quota for protected domain names.

If you want to add two different top-level domains or their subdomains to connect to the Anti-DDoS Premium instance, you need to expand the quota for protected domain names. Assume that you have added `abc.com` or its subdomain for protection, when you try to add `xyz.com` \(another top-level domain\) or its subdomain, you will receive the following message:

```
The quota of top-level domains has been exceeded. Upgrade the instance to expand the quota for protected domain names.
```

In this case, you need to upgrade the Anti-DDoS Premium instance to expand the quota for domain name mitigation.

**Note:** Adding 10 protected domain names each time allows you to have one more top-level domain in the quota for domain name mitigation. For example, you must set the number of protected domain names to 20 to protect the two top-level domains,`abc.com` and `xyz.com` in an Anti-DDoS Premium instance.

