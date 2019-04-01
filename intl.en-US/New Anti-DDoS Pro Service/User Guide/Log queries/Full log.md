# Full log {#concept_98586_zh .concept}

Integrated with Log Service, Alibaba Cloud Anti-DDoS Pro now supports real-time analysis of access logs and attack logs, and provides a report center with a variety of reports.

According to the [2017 APNIC DDoS threat landscape](https://blog.apnic.net/2018/04/03/the-DDoS-threat-landscape-in-2017/) report, more than 80% of DDoS attacks are combined with HTTP flood attacks, which can be quite difficult to detect. It is especially important to analyze access logs in real time to identify attack behavior and apply a protection policy in a timely manner.

After you set up Anti-DDoS Pro for your website, Log Service collects access logs and attack logs in real time, allows you to query and analyze log data, and displays query results in dashboards.

## Enable full log {#section_brn_bn3_kgb .section}

To enable full log for your website, perform the following steps:

**Note:** By default, full log retains log data for 30 days with a maximum of 3 TB storage capacity for free. More storage configurations will be available soon. You may upgrade to a higher storage configuration based on your needs. Additional fees will be charged for higher storage configurations.

**Notice:** 

-   When the maximum storage capacity is reached, new log data is not saved. You have three chances to delete all log data. You can also choose not to save log data from unnecessary websites.
-   The free storage configuration retains log data for 30 days by default. Log data that is more than 30 days old is automatically overwritten by new log data.

1.  Log on to the [Anti-DDoS Pro](https://yundunnext.console.aliyun.com/?p=ddoscoo) console. In the left-side navigation pane, choose **System** \> **Full Log**.

    **Note:** If you have not enabled full log, the following message appears when you log on to the Anti-DDoS Pro console. You can click **View Details** to enable full log.

2.  Click **Enable Now** and authorize Anti-DDoS Pro to save your log data to your exclusive logstore in Log Service.

    **Note:** If you have not activated Log Service, you can activate Log Service for free when you enable full log.

3.  On the Full Log page, select a domain and click Status to enable full log for the selected domain.

After you enable full log, you can query and analyze log data in real time, view and edit dashboards, and set monitoring alarms on the Full Log page.

## Scenarios { .section}

After full log is enabled, you can use it in the following scenarios.

-   **Troubleshoot exceptions**

    You can query and analyze log data in real time. You can use SQL statements to analyze the access logs on your website. This allows you to quickly troubleshoot and analyze access exceptions, and view information about read/write latency and the distribution of ISPs.

    For example, you can use the following statement to view access logs on your website:

    `__topic__: DDoS_access_log`

-   **Track attack sources**

    Access logs record information about the source and distribution of HTTP flood attacks. You can query and analyze access logs in real time to track attack sources, helping you select the most effective protection strategy.

    -   For example, you can use the following statements to analyze the geographical distribution of HTTP flood attacks:

        `__topic__: DDoS_access_log and cc_blocks > 0| SELECT ip_to_country(if(real_client_ip='-', remote_addr, real_client_ip)) as country, count(1) as "Number of Attacks" group by country`

    -   For example, use the following statement to view PVs:

         `__topic__: DDoS_access_log | select count(1) as PV`

-   **Analyze site operations**

    Access logs record information about website traffic in real time. You can use SQL queries to analyze log data and better understand your users. For example, you can find the most visited webpages, the source IPs of the clients, the browsers that initiated the requests, and the distribution of client devices, which can help you analyze site operations.

    For example, you can use the following statements to view the distribution of traffic by ISP:

    `__topic__: DDoS_access_log | select ip_to_provider(if(real_client_ip='-', remote_addr, real_client_ip)) as provider, round(sum(request_length)/1024.0/1024.0, 3) as mb_in group by provider having ip_to_provider(if(real_client_ip='-', remote_addr, real_client_ip)) <> '' order by mb_in desc limit 10`


