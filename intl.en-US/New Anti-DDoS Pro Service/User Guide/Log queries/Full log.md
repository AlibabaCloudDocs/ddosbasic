# Full log {#concept_98586_zh .concept}

Alibaba Cloud Anti-DDoS Pro is now integrated with Log Service to provide real-time analysis and reports of access and attack logs.

The [APNIC DDoS threat landscape in 2017](https://blog.apnic.net/2018/04/03/the-DDoS-threat-landscape-in-2017/) states that more than 80% of DDoS attacks are combined with HTTP flood attacks, which can be difficult to detect. Hence, it is important to analyze access logs in real time to identify attack behaviors and apply a suitable protection policy in a timely manner.

After you set up Anti-DDoS Pro for your website, Log Service starts to collect access logs and attack logs in real time. You can query and analyze log data collected by Anti-DDoS Pro, and the results are displayed as easy-to-read dashboards.

## Activate the full log service {#section_tsj_h3f_g30 .section}

Perform the following steps to activate the Anti-DDoS Pro full log service:

**Note:** The Anti-DDoS Pro full log service is in the open beta phase. The open beta will end on April 30, 2019. During the open beta phase, full log retains log data of up to 3 TB for 30 days for free. If you want to continue using the full log service after the open beta, you will be billed based on storage specifications.

1.  Log on to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo). In the left-side navigation pane, choose **System** \> **Full Log**. Click **Enable Now** to go to the [full log service purchase page](https://common-buy.aliyun.com/?commodityCode=ddos_fl_pre#/buy).
2.  Select a storage capacity and a service duration based on your business needs.

    -   **Log Storage**: the log storage capacity. Unit: TB.

        When the log storage capacity you purchase is full, new logs cannot be stored. We recommend that you monitor the remaining log storage space and expand the storage space preemptively.

    -   **Duration**: the validity period of the full log service.

        After the full log service expires, new logs cannot be stored. If you do not renew the full log service within seven days after it expires, all log data will be automatically deleted.

    **Note:** If the full log service has sufficient storage capacity while it is valid, it will store the logs of 180 consecutive days starting from the day the full log service is enabled. Logs from day 181 will overwrite the logs from day 1. Logs from subsequent days will overwrite logs from the next earliest dates. Therefore, with sufficient storage capacity, only full logs of the last 180 days are stored.

    **Example of how to select a log storage capacity**

    Typically, each request log occupies about 2 KB of storage space. If the average request volume of your business is 500 queries per second \(QPS\), the storage space required for one day is: 500 x 60 x 60 x 24 x 2 = 86,400,000 KB \(82 GB\). The default storage period is 180 days. To store logs of the last 180 days, you need to select a log storage capacity of 14,832 GB \( 14.5 TB\).

3.  Click **Buy Now** and complete the payment.

After the full log service is activated, you can go to the Log Service page and click **Details** to view the service specifications.

**Note:** We recommend that you monitor the remaining log storage space and validity period during use. When the utilization of the log storage capacity reaches 70%, expand the log storage capacity to make sure that new logs can be stored.

## Enable the full log service {#section_brn_bn3_kgb .section}

To enable the full log service for your protected website domain in Anti-DDoS Pro, perform the following steps:

1.  Log on to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo). In the left-side navigation pane, choose **System** \> **Full Log**.
2.  Click **Enable Now**. Follow the on-screen prompts to authorize Anti-DDoS Pro to store logs in your dedicated logstore.
3.  On the Full Log page, select the target domain and turn on Status to enable full log for the selected domain.

After you enable full log, you can query and analyze the collected logs in real time, view and edit dashboards, and set monitoring alerts on the Full Log page.

## Scenarios { .section}

Anti-DDoS Pro full log is applicable to the following scenarios:

-   **Troubleshoot website access problems** 

    After Anti-DDoS Pro full log is enabled for your website, you can query and analyze the logs collected from your website in real time. You can use SQL statements to analyze the access logs on your website. This allows you to quickly troubleshoot and analyze access problems, and view information about read/write latency and the distribution of ISPs.

    For example, the following statement can be used to view access logs on your website:

    `__topic__: DDoS_access_log`

-   **Track HTTP flood attack sources** 

    Access logs record information about the sources and distribution of HTTP flood attacks. You can query and analyze access logs in real time to identify the origins of attacks, and use this information to select the most effective protection strategy.

    -   For example, the following statement can be used to analyze the geographical distribution of HTTP flood attacks:

        `__topic__: DDoS_access_log and cc_blocks > 0| SELECT ip_to_country(if(real_client_ip='-', remote_addr, real_client_ip)) as country, count(1) as "number of attacks" group by country`

    -   For example, the following statement can be used to view PVs:

        `__topic__: DDoS_access_log | select count(1) as PV`

-   **Analyze website operations** 

    Access logs record information about website traffic in real time. You can use SQL queries to analyze log data and better understand your users. For example, you can identify the most visited web pages, the source IP addresses of the clients, the browsers that initiated the requests, and the distribution of client devices, which can help you analyze website operations.

    For example, the following statement can be used to view the distribution of traffic by ISP:

    `__topic__: DDoS_access_log | select ip_to_provider(if(real_client_ip='-', remote_addr, real_client_ip)) as provider, round(sum(request_length)/1024.0/1024.0, 3) as mb_in group by provider having ip_to_provider(if(real_client_ip='-', remote_addr, real_client_ip)) <> '' order by mb_in desc limit 10`


