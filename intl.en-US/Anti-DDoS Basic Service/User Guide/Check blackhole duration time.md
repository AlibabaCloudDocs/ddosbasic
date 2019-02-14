# Check blackhole duration time {#task512 .task}

When your server suffers massive DDoS attacks and the blackhole mechanism is triggered, the public IP of the server is banned for a certain time period based on the security credibility of the server.

The default blackhole duration time is 2.5 hours and the IP cannot be unbanned during this period. The actual blackhole duration time depends on the attack situation and may range from 30 minutes to 24 hours. The duration time of the blackhole status is mainly influenced by the following factors:

-   Whether the attack persists. The blackhole duration time keeps extending, if the attack continues. The blackhole duration time is re-calculated from the time of extension.
-   Whether the attack is frequent. If a user is attacked for the first time, the blackhole duration time will be automatically shortened. On the contrary, the blackhole duration time for a user under frequent attacks will be automatically extended as the user is more likely to be attacked again.

You can log on to the Anti-DDoS Basic console to view the specific blackhole threshold and duration time.

**Note:** 

-   For users suffering overly frequent blackholes, Alibaba Cloud reserves the right to extend the blackhole duration time and reduce the blackhole threshold.
-   Blackhole is a service provided by Internet service providers \(ISPs\) and ISPs have a clear time limit to the blackhole deactivation. Thus, in general, the blackhole duration time is no less than 30 minutes, and the specific blackhole duration time of your account is automatically adjusted according to the security credibility of your account.

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  On the **Anti-DDoS Basic** \> **Instance** page, turn on the **DDoS Attack Protection Information** switch in the upper right corner. 
3.  View the current blackhole duration time.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79454/154814197634165_en-US.png)

 

