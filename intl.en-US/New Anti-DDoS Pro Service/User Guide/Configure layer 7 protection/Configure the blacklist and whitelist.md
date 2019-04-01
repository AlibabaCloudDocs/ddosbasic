# Configure the blacklist and whitelist {#concept_72218_zh .concept}

Anti-DDoS Pro allows you to configure a blacklist and whitelist to control access to your domain.

-   You can use the whitelist to allow access to a list of IPs and CIDR blocks without further inspection.
-   You can use the blacklist to deny access to a list of IPs and CIDR blocks.

**Note:** The configurations of the blacklist and whitelist are effective for single domains, not Anti-DDoS Pro instances. For each domain, you can add up to 200 entries in the blacklist and whitelist respectively. You can enter either IP addresses or CIDR blocks in the blacklist and whitelist.

To block IPs that send a large number of malicious requests to your server, you can add them to the blacklist. Meanwhile, you can add internal CIDR blocks, service interface IPs, and verified IPs to the whitelist so that requests from these IPs are not blocked.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo#/).
2.  In the left-side navigation pane, choose **Management** \> **Websites**, select a domain, and click **Protection Settings**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79693/155411461036924_en-US.png)

3.  In the **Blacklist and Whitelist** area, click **Change Settings**.

    **Note:** To configure the blacklist or whitelist, you must enable HTTP flood protection.

    -   Click the **Blacklist** tab, enter the IP addresses or CIDR blocks that you want to block, and click **OK**.
    -   Click the **Whitelist** tab, enter the IP addresses or CIDR blocks that you want to allow access to, and click **OK**.
    **Note:** You can enter up to 200 entries in the blacklist and whitelist respectively. Each entry can be an IP address or CIDR block. Separate multiple entries with commas \(,\).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79693/155411461036925_en-US.png)


**Note:** 

-   The blacklist and whitelist feature is only available in domain configurations.
-   The configurations of the blacklist and whitelist take effect immediately after creation.

    **Notice:** In some situations, it may take a few minutes for the configurations to take effect. If the configurations of the blacklist and whitelist do not take effect immediately, wait a few minutes.

-   You can add 0.0.0.0/0 to the blacklist, which blocks requests from all IP addresses except the ones listed in the whitelist.
-   Once created, the configurations of the blacklist and whitelist are effective for all Anti-DDoS Pro instances that are associated with the specified domain.

