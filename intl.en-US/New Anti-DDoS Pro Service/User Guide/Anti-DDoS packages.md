# Anti-DDoS packages {#concept_xrw_4nl_zgb .concept}

Anti-DDoS Pro provides anti-DDoS packages as a value-added service to help you reduce the cost of defending against DDoS attacks.

## What is an anti-DDoS package {#section_c3c_wnl_zgb .section}

In most scenarios, when the bandwidth during a DDoS attack exceeds the basic bandwidth provided by your Anti-DDoS Pro instance, the burstable bandwidth is consumed or the black hole is triggered if you set the burstable bandwidth and basic bandwidth to the same value.

-   If your service survived the attack after the burstable bandwidth is consumed, additional fees will be charged based on the difference between the peak attack bandwidth and basic bandwidth. Click here to view [billing methods](intl.en-US/New Anti-DDoS Pro Service/Pricing/Billing methods.md#table_jfs_2jb_kgb). This method involves increased cost to maintain the security of your service.
-   If you set the burstable bandwidth and basic bandwidth to the same value, when the attack bandwidth exceeds the basic bandwidth, the black hole is triggered and your service is interrupted till the black hole status is lifted. This method may affect the performance of your service but does not incur additional fees.

Anti-DDoS packages can help you defend against DDoS attacks when the attack bandwidth exceeds the basic bandwidth without incurring any additional cost. Each anti-DDoS package has two parameters: bandwidth and available protections. For example, if an anti-DDoS package has 300 Gbit/s bandwidth and 3 available protections,

-   you can use this anti-DDoS package to offset the fees incurred from defending against attacks whose maximum bandwidth reaches the sum of 300 Gbit/s and your basic bandwidth. If the attack bandwidth is greater than the sum of 300 Gbit/s and your basic bandwidth, you cannot use this anti-DDoS package to offset additional fees. Based on the [billing methods](intl.en-US/New Anti-DDoS Pro Service/Pricing/Billing methods.md#), additional fees may be charged to your account.
-   you can use this anti-DDoS package to offset additional fees up to three times. Each time you use an anti-DDoS package, it is valid for the entire day.

**Notes**

Note the following details when you use anti-DDoS packages:

-   Anti-DDoS packages do not improve the protection capability of Anti-DDoS Pro. You can only use anti-DDoS packages to offset the fees incurred by consuming burstable bandwidth. The protection capability of Anti-DDoS Pro is dependent on the basic and burstable bandwidth settings.

    We recommend that users who have anti-DDoS packages increase the burstable bandwidth so that you can actually take advantage of anti-DDoS packages. You can set the burstable bandwidth to the sum of the basic bandwidth and anti-DDoS package bandwidth.

    For example, if your basic bandwidth is 30 Gbit/s and you have an anti-DDoS package with 300 Gbit/s bandwidth, we recommend that you set the burstable bandwidth to 330 Gbit/s.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134871/155411481540097_en-US.png)

-   You can only use anti-DDoS packages to offset additional fees when the peak attack bandwidth is no greater than the sum of the basic bandwidth and anti-DDoS package bandwidth.
-   When the number of available protections of your anti-DDoS package is reduced to zero, we recommend that you set the burstable bandwidth to the same as the basic bandwidth to avoid additional fees.
-   You can only use anti-DDoS packages to offset additional fees that are billed no earlier than the day you obtained the anti-DDoS packages.

|Item|Older version|Current version|
|----|-------------|---------------|
|Conditions of use|Must be associated with Anti-DDoS Pro instances.|No need to be associated with Anti-DDoS Pro instances. The anti-DDoS package that has the shortest expiration time is automatically used.|
|Intended use|Offset additional fees that are incurred from defending against attacks whose maximum bandwidth is no greater than the anti-DDoS package bandwidth.|Offset additional fees that are incurred from defending against attacks whose maximum bandwidth is no greater than the sum of the anti-DDoS package bandwidth and your basic bandwidth.|

## How to obtain anti-DDoS packages {#section_q34_5nl_zgb .section}

Currently, anti-DDoS packages are provided to qualified users as a value-added service. If you meet one of the following conditions, you can contact customer service to obtain anti-DDoS packages for free:

-   It is the first time that you activated Anti-DDoS Pro.
-   You have been continuously using Anti-DDoS Pro for three months or more.
-   You have purchased a yearly subscription.

## How to use anti-DDoS packages {#section_px4_rnl_zgb .section}

Anti-DDoS packages are automatically applied when DDoS attacks trigger protection policies. You can view records of your anti-DDoS packages in the Anti-DDoS Pro console. Anti-DDoS packages are only valid when they are not expired, and the number of available protections is larger than zero.

You can view the records of your anti-DDoS packages using the following steps:

1.  Log on to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo#/report).
2.  In the left-side navigation pane, choose **Management** \> **Anti-DDoS Package** to view all anti-DDoS packages.

    -   **Anti-DDoS Package ID**: The unique identifier of the anti-DDoS package.
    -   **Size**: The bandwidth of the anti-DDoS package.
    -   **Expire Time**: The expiration time of the anti-DDoS package.
    -   **Status**: The anti-DDoS package status, including valid, exhausted, and expired.
    -   **Available Protections**: The number of times you can use the anti-DDoS package.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134871/155411481540098_en-US.png)

3.  Select an anti-DDoS package and click **View Log** under the Actions column to view logs about the anti-DDoS package.

