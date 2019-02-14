# Anti-DDoS Basic black hole threshold {#concept_40033_zh .concept}

Anti-DDoS Basic may actively trigger a black hole to lock network access to the instance if the data transfer rate exceeds the default black hole threshold \(unit: bps\). Once in a black hole, the instance under attack cannot be unblocked. See the following table for the default threshold settings for different regions.

**Note:** 

-   The default threshold settings apply to ECS, SLB, and EIP.
-   The actual black hole threshold of your ECS, SLB, or EIP instance also indicates the type and network bandwidth of the instance, and is subject to the threshold in the Alibaba Cloud console. For more information, see [How to check the black hole threshold of your instance?](#)

|Region|Solo-Core CPU ECS|Duo-Core CPU ECS|Quad-Core or higher CPU ECS|SLB and EIP|
|------|-----------------|----------------|---------------------------|-----------|
|East China 1|500 M|1 G|5 G|5 G|
|East China 2|500 M|1 G|2 G|2 G|
|North China 1|500 M|1 G|5 G|5 G|
|North China 2|500 M|1 G|2 G|2 G|
|North China 3|500 M|1 G|2 G|2 G|
|South China 1|500 M|1 G|2 G|2 G|
|Hong Kong|500 M|500 M|500 M|500 M|
|US East 1|500 M|1 G|2 G|2 G|
|US West 1|500 M|500 M|500 M|500 M|
|Tokyo|500 M|500 M|500 M|500 M|
|Singapore|500 M|500 M|500 M|500 M|
|Sydney|500 M|500 M|500 M|500 M|
|Kuala Lumpur|500 M|500 M|500 M|500 M|
|Mumbai|500 M|1 G|1 G|1 G|
|Frankfurt|500 M|500 M|500 M|500 M|
|Dubai|500 M|500 M|500 M|500 M|

The black hole duration is the amount of time the triggered black hole lasts, 2.5 hours by default. The actual black hole duration varies from 30 minutes to 24 hours, depending on attack intensity. Additionally, the following factors are considered:

-   Attack Continuity. The black hole duration is extended, if the attack continues.
-   Attack Frequency. The black hole duration is shortened automatically when the ECS instance is attacked for the first time, but can be prolonged accordingly, if under frequent attacks.

**Note:** If an ECS instance triggers too many black holes, Alibaba Cloud Security reserves the right to extend the black hole duration and lower its threshold. You can check the actual duration and threshold information in Alibaba Cloud Anti-DDoS Basic console.

## How to check the black hole threshold of your instance? {#view .section}

To check the actual black hole threshold of your ECS, SLB, or EIP instance, follow these steps:

1.  Log on to [Alibaba Cloud Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext).
2.  Select the region.
3.  On the **Anti-DDoS Basic** \> **Instances** page, select the instance type tab: **ECS**, **SLB**, or **EIP \(including NAT\)**.
4.  Locate the instance, and check the actual black hole threshold of the instance in the **Current Protection Threshold** column.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79459/154806168834180_en-US.png)


