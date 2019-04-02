# Configure layer 4 smart defense settings {#concept_92302_zh .concept}

Anti-DDoS Pro provides the smart defense feature to help you defend against layer 4 DDoS attacks. This feature supports three modes for you to choose from. You can change the smart defense mode based on your needs. Once changed, the selected mode takes effect within a few minutes.

The smart defense feature supports the following modes:

-   **Low**: This mode automatically identifies and scrubs traffic that displays common attack patterns based on historical traffic patterns and years of experience defending against Web attacks. The mode is based on an algorithm that automatically identifies malicious IP addresses and adds them to the blacklist. This mode may not be able to block all layer 4 floods but has a low false positive rate.
-   **Normal**: This mode automatically identifies and scrubs traffic that displays common and likely attack patterns based on historical traffic patterns and years of experience defending against Web attacks. We recommend that you use this mode in most situations as it maintains an optimal balance between protection and false positives.
-   **Strict**: This mode provides the most rigorous protection against ongoing attacks based on historical traffic patterns and years of experience defending against Web attacks. The mode may cause false positives.

The normal mode is enabled by default. Smart defense bases its decisions on historical traffic pattern data. If this is the first time that you have set up Anti-DDoS Pro to protect your business, it takes Anti-DDoS Pro about three days to learn your traffic pattern in order to provide the best protection.

You can view or delete the IP addresses that are automatically added to the blacklist by smart defense. You can also manually add other malicious IP addresses to the blacklist. Meanwhile, you can add specific IP addresses to the whitelist so that Anti-DDoS Pro allows access to these IP addresses without further inspection.

## Change smart defense modes { .section}

After you buy an Anti-DDoS Pro instance, the smart defense feature is enabled and the normal mode is used by default. You can change smart defense modes based on your needs.

1.  Log on to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo#/report).
2.  Choose **Protection** \> **Protection Settings** \> **Anti-DDoS Protection Policies** \> **Scrubbing Mode**, select an Anti-DDoS Pro instance, and click **Modify Smart Defense Mode**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79690/155411457036903_en-US.png)

    **Note:** The smart defense feature is enabled by default. You can click the switch to disable smart defense.

3.  Change the smart defense mode based on your needs and click **OK**.

    **Note:** The selected mode takes effect within a few minutes.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79690/155411457036904_en-US.png)


## Manage the blacklist and whitelist { .section}

You can view and manage the IP addresses that are added to the blacklist by smart defense. You can also add specific IP addresses to the whitelist so that Anti-DDoS Pro allows access to these IP addresses without further inspection.

-   The blacklist

    Choose **Protection** \> **Protection Settings** \> **Anti-DDoS Protection Policies** \> **Blacklist and Whitelist**, click **Blacklist**, and select Anti-DDoS Pro to view and manage all IP addresses in the whitelist under the instance.

    **Note:** Each IP address in the blacklist has an expiration time. An IP address is automatically removed from the blacklist when its expiration time is reached. Smart defense automatically specifies an expiration time when it adds an IP address to the blacklist. The expiration time ranges from 5 minutes to 1 hour. If a blacklisted IP address continuously sends malicious requests before the expiration time is reached, Anti-DDoS Pro automatically extends the expiration time. You also need to specify an expiration time when you manually add an IP address to the blacklist.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79690/155411457036905_en-US.png)

    You can perform the following operations on the blacklist:

    -   **Search by keyword**: Enter a keyword in the search box and click the search icon to search for specific IP addresses in the blacklist.
    -   **Download**: Click **Download** to download all blacklisted IP addresses to your local computer.
    -   **Clear Blacklist**: Click **Clear Blacklist** to remove all blacklisted IP addresses.
    -   **Manually Add**: Click **Manually Add** to manually add IP addresses to the blacklist. You need to specify an expiration time for each IP address.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79690/155411457036906_en-US.png)

        **Note:** You can manually add up to 2,000 IP addresses to the blacklist.

-   The whitelist

    Choose **Protection** \> **Protection Settings** \> **Anti-DDoS Protection Policies** \> **Blacklist and Whitelist**, click **Whitelist**, and select an Anti-DDoS Pro instance to manage the whitelist under the instance.

    **Note:** The IP addresses in the whitelist can only be removed manually. The whitelist has a higher priority over the blacklist. If an IP address is already listed in the whitelist, this IP address cannot be added to the blacklist.

    You can perform the following operations on the whitelist:

    -   **Search by keyword**: Enter a keyword in the search box and click the search icon to search for specific IP addresses in the whitelist.
    -   **Download**: Click **Download** to download all whitelisted IP addresses to your local computer.
    -   **Clear Whitelist**: Click **Clear Whitelist** to remove all whitelisted IP addresses.
    -   **Manually Add**: Click **Manually Add** to manually add IP addresses to the whitelist.

        **Note:** You can add up to 500 IP addresses to the whitelist.


