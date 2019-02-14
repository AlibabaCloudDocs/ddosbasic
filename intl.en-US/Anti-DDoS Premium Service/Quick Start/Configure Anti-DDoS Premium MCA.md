# Configure Anti-DDoS Premium MCA {#task1328 .task}

Anti-DDoS Premium mainland China acceleration \(MCA\) instance is used together with Anti-DDoS Premium Insurance/Unlimited instance, to realize quick access to your web service that deployed outside mainland China, especially for your Mainland China users.

After configuring MCA instance together with Anti-DDoS Premium Insurance/Unlimited instance, your web service can have the following features: Under no DDoS attack happens, Anti-DDoS Premium enables the MCA instance to accelerate web access to your service. When DDoS attack happens, Anti-DDoS Premium automatically switches to the anti-DDoS instance \(Insurance/Unlimited instance\) to mitigate DDoS attacks for your web service.

For more information about recommended scenarios that require Anti-DDoS Premium MCA, refer to [Anti-DDoS Premium Use Cases](reseller.en-US/Anti-DDoS Premium Service/Product Introduction/Scenarios.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79672/154780976335306_en-US.png)

You can configure an Anti-DDoS Premium MCA instance for domain \(7-layer\) or port \(4-layer\).

After purchasing Anti-DDoS Premium MCA and Insurance/Unlimited instances, complete provisioning of the instances for your website domain or service port on the Anti-DDoS Premium Management console, and then configure a Security Traffic Manager rule to enable the auto-switching between MCA and anti-DDoS instances. Finally, use the security service manager rule to forward non-attack traffic to the origin server of your web service.

1.  Log on to the [Anti-DDoS Premium Service console](https://partners-intl.console.aliyun.com/#/ddosdip). 
2.  Add your website or non-website service to both Anti-DDoS Premium Insurance/Unlimited and MCA instances. 

    **Note:** Only complete the provisioning configurations for your web service. Do not change the DNS resolution records of your domain at this step.

    -   For website domain: Refer to [Add website to Anti-DDoS Premium for protection](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Add website to Anti-DDoS Premium for protection.md#) to complete the provisioning configuration. During the configuration, choose both dedicated IPs of your Insurance/Unlimited and MCA instances when you choose dedicated IPs of Anti-DDoS Premium.

    -   For service port: Refer to [Add non-website business to Anti-DDoS Premium for protection](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Add a non-website business to Anti-DDoS Premium for protection.md#) to complete the provisioning configuration. Add forwarding rules under both Anti-DDoS Premium Insurance/Unlimited and MCA instances for your non-website service. Thus, you have to add a forwarding rule for your non-website service for each instance that is supposed to be used.

**Note:** To configure Anti-DDoS Premium MCA for non-website service, your service must have a domain bound with the origin server instead of using the server IP directly. Otherwise, traffic cannot be automatically scheduled by Security Traffic Manager.

3.  After the provisioning configuration completes, select the **Provisioning** \> **Security Traffic Manager** page, click **Add Rule**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79672/154780976335308_en-US.png)

4.  In the Add Rule dialog box, configure rule and then click **Confirm**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79672/154780976335312_en-US.png)

    -   The High Priority node: select the dedicated IP of the MCA instance.
    -   The Low Priority node: select the dedicated IP of the Insurance/Unlimited instance.
    With this configuration, MCA instance is enabled with a high priority to accelerate web access when no DDoS attack happens, and the Security Traffic Manager automatically switch traffic to the anti-DDoS instance for DDoS attack mitigation when under DDoS attacks.

    The system generates a CNAME record when the security traffic manager rule is added. After you change the DNS records of your service domain to resolve to the CNAME, the service traffic manager enables the traffic auto-scheduling for your service.

    **Note:** For those dedicated IPs that you select in the security traffic manager rule, make sure that you have completed the provisioning configurations for the dedicated IPs of the MCA and Insurance/Unlimited instances.

5.  In the domain name resolution service provider, modify the DNS resolution record for that domain name. After the DNS configuration is effective, all traffic to your web service is handled by the security traffic manager for auto-scheduling.

    **Note:** The traffic auto-scheduling is based on the CNAME record. Therefore, the DNS resolution of the service domain must use the CNAME record.


