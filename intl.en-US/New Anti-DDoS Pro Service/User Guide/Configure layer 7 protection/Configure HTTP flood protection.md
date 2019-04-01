# Configure HTTP flood protection {#concept_72210_zh .concept}

Anti-DDoS Pro provides four protection modes to help you defend against HTTP flood attacks.

-   **Normal**: The default HTTP flood protection mode. We recommend that you use this mode when the traffic pattern on your website is normal.

    This mode defends against typical HTTP flood attacks and does not block normal requests.

-   **Emergency**: You can enable this mode when you notice HTTP response errors, traffic anomalies, or CPU and memory usage spikes.

    The emergency mode provides relatively rigorous protection. This mode can defend against more complicated flood attacks, but may mistakenly block a small number of normal requests.

-   **Strict**: This mode provides rigorous protection against HTTP flood attacks. The mode uses captcha verification to verify the identity of all visitors. Only verified visitors are allowed to access the site.

    **Note:** The strict mode is built on a verification mechanism that verifies whether the request is sent from a browser by a real user. If this mode is enabled for API services and native applications, false positives may occur, disrupting the availability of your service.

-   **Super Strict**: This mode provides the most rigorous protection against HTTP flood attacks. The mode uses captcha verification to verify the identity of all visitors. Only verified visitors are allowed to access the site.

    Compared with the strict mode, this mode combines captcha verification with anti-debugging techniques to enhance the protection of your site.

    **Note:** The super strict mode is built on a verification mechanism that verifies whether the request is sent from a browser by a real user. In very rare situations, a browser error may occur and cause service interruptions. Users only need to restart the browser to resolve this issue. However, if this mode is enabled for API services and native applications, false positives may occur, disrupting the availability of your service.


## Procedure {#section_cyy_rj3_kgb .section}

By default, normal HTTP flood protection is used. You can change protection modes based on your needs.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo#/).
2.  In the left-side navigation pane, choose **Management** \> **Websites**, select a domain, and click **Protection Settings**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79692/155411459536921_en-US.png)

3.  In the **HTTP Flood Protection** area, select a protection mode.

    **Note:** You can click Status to disable HTTP flood protection.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79692/155411459536922_en-US.png)


## Custom rules { .section}

The HTTP flood protection feature also allows you to create custom rules to defend against HTTP flood attacks. You can add custom rules to protect specific URLs.

On the Protection Settings page, find the **HTTP Flood Protection** area and enable custom rules. You can then click **Change Settings** to create custom rules.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79692/155411459536923_en-US.png)

## Best practices for HTTP flood protection { .section}

The protection effects provided by different protection modes are as follows: Super Strict \> Strict \> Emergency \> Normal. The chances of false positives when using these protection modes are as follows: Super Strict \> Strict \> Emergency \> Normal.

In normal situations, we recommend that you use the normal HTTP flood protection mode to protect your site. This mode only blocks IP addresses that frequently send requests to your website. We recommend that you enable the emergency or strict mode when your website is overwhelmed by flood attacks and the normal protection mode fails to protect your site.

**Note:** For API services and native applications, you cannot use the strict or super strict mode because false positives are likely to occur. You can instead create custom rules to protect specific URLs from flood attacks.

