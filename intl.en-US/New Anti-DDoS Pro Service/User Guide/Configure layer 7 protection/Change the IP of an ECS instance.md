# Change the IP of an ECS instance {#task673 .task}

If your origin server IP is exposed, we recommend that you deploy your service on an ECS instance to prevent attackers from bypassing Anti-DDoS Pro and hacking into your server. You can change IPs of ECS instances up to 10 times in the Anti-DDoS Pro console.

**Note:** You can only change public IPs of ECS instances that are connected to classic networks.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?&p=ddoscoo&__consolePageCode=ddoscoo#/). 
2.  In the left-side navigation pane, choose **Management** \> **Websites**. 
3.  Click **Change ECS IP**. 

    **Notice:** When you change the IP of an ECS instance, your service deployed on the instance is interrupted for a few minutes. We recommend that you back up your data in advance.

4.  You must stop an ECS instance if you want to change its IP address. If the target ECS instance is stopped, go to step 6. In the Change ECS IP dialog box, click **Go to ECS** to stop the target ECS instance in the ECS console. 
    1.  In the instances list, select the target ECS instance and click its instance ID. 
    2.  On the instance details page, click **Stop** in the upper-right corner. 
    3.  Select a stop method and click **OK**. 

        **Notice:** To stop the instance, you must pass SMS verification.

    4.  Wait until the target ECS instance is **Stopped**. 
5.  Return to the Change ECS IP dialog box, enter the **ID of the target ECS instance**, and click **Next**. 
6.  Make sure you have selected the right ECS instance and click **Release IP**. 
7.  After the original IP address is released, click **Next** and the system assigns a new IP address to the instance. 
8.  Click **OK**. 

    **Note:** After you change the IP of an ECS instance, configure Anti-DDoS Pro to protect the instance and make sure the new IP address is not exposed to the public.


