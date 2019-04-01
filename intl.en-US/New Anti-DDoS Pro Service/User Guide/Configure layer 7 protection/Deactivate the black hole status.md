# Deactivate the black hole status {#task664 .task}

After your website is configured in Anti-DDoS Pro, incoming traffic to your site is forwarded to a black hole when the attack bandwidth exceeds your basic or burstable bandwidth. To restore your service, you can deactivate the black hole status in the Anti-DDoS Pro console. Each user can deactivate the black hole status up to five times every day.

To avoid activating a black hole multiple times, we recommend that you increase your basic or burstable bandwidth before you deactivate the black hole status.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?&p=ddoscoo&__consolePageCode=ddoscoo#/). 
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings**. 
3.  Click Anti-DDoS Protection Policies and select **Deactivate Black Hole**. 

    **Note:** 

    -   Each user can deactivate the black hole status up to five times every day. This quota is reduced by one each time the black hole status is successfully lifted.
    -   When you deactivate the black hole status for the first time that day, the black hole status is immediately lifted. When you deactivate the black hole status consecutively, the time interval between each operation must be no less than 10 minutes.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79694/155411462336926_en-US.png)

4.  Select the Anti-DDoS Pro instance that is in black hole status. Check **the time before the black hole status is automatically lifted**. You can also click **Deactivate** under the Actions column to manually deactivate the block hole status. 
    -   The black hole status is a risk management strategy used by the backend services of Alibaba Cloud. Attempts to deactivate the black hole status may fail, which does not reduce your quota for manually deactivating the block hole status. If an attempt to deactivate the black hole status fails, an error message appears. You can try to deactivate the black hole status later.
    -   If the message "Cannot deactivate the black hole status due to risk management. Wait 10 minutes and try again." appears, please wait and try again later.
    -   If no error message appears, the black hole status is lifted. You can refresh the page to check if network access is restored.

