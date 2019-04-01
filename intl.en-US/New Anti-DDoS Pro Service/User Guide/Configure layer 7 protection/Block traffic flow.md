# Block traffic flow {#task799 .task}

Anti-DDoS Pro allows you to block overseas traffic transmitted through China Telecom and China Unicom networks. Overseas traffic is any traffic originating from countries and regions outside mainland China. Each user can block overseas traffic up to 10 times and unblock traffic at any time.

We recommend that you block overseas traffic when your service is suffering DDoS attacks and the attack bandwidth is likely to exceed your burstable bandwidth. If overseas traffic accounts for 30% of the attack bandwidth, you can block overseas traffic to quickly bring the attacks under control.

Once blocked, overseas traffic is discarded at the Anti-DDoS scrubbing center. This lowers the chance of triggering a black hole when the Anti-DDoS Pro instance is overwhelmed by attack traffic. Anti-DDoS Pro takes multiple factors into account when it comes to activating a black hole, such as the attack bandwidth and the source of the attack traffic. Blocking overseas traffic can to some degree reduce the chance of triggering a black hole.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?&p=ddoscoo&__consolePageCode=ddoscoo#/). 
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings**. 
3.  On the Anti-DDoS Protection Policies page, click **Block Flow**. ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79695/155411467036930_en-US.png)

 
4.  Select the Anti-DDoS Pro instance and network type, and click **Block**. 

    **Note:** 

    -   You can block overseas traffic transmitted through China Telecom and China Unicom networks. We recommend that you block traffic transmitted through China Telecom networks first and observe the trend of attacks. If the attack bandwidth is still increasing, you can then block traffic transmitted through China Unicom networks.
    -   Each user can block overseas traffic up to 10 times. This quota is reduced by one each time you block traffic transmitted through China Telecom or China Unicom networks.
5.  In the Block Traffic Flow dialog box, select the **blocked region** and the **blocking duration**, and click **Confirm**. Currently, you can only select the international region. 

    **Note:** The blocking duration can range from 15 minutes to 23 hours and 59 minutes.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79695/155411467036931_en-US.png)

6.  Click Confirm. 
    -   If an error occurs when blocking overseas traffic, an error message appears. Resolve the issue and try again later.
    -   If no error message appears, overseas traffic is blocked. Refresh the page and you can find the blocked region and blocking duration. The block button is replaced by **Unblock**. To immediately unblock traffic, click **Unblock** under the Actions column.

