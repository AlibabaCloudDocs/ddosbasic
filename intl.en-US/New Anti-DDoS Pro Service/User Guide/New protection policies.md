# New protection policies {#concept_uqh_gwc_bhb .concept}

Anti-DDoS Pro provides the following new features to help you defend against HTTP flood attacks: Geo-blocking, Accurate Access Control, and Intelligent Protection. Meanwhile, Web Acceleration is now available to speed up your website.

**Note:** Currently, new protection policies are in beta testing until May 31, 2019.

## Enable new protection policies {#section_axx_m1f_bhb .section}

During the beta testing period, HTTP flood protection policies only include two features by default: Blacklist and Whitelist, and HTTP Flood Protection.

To start using new protection policies, perform the following steps:

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings**, select your domain, and click **Try out New Protection Policies**.
3.  In the dialog box that appears, read the note and click **OK**.

    **Note:** 

    -   After you start using the new protection policies, your Anti-DDoS Pro instance uses a new CIDR block to forward traffic back to your origin server. If you have configured access control policies on your origin server, make sure to add the new CIDR block to the whitelist.
    -   To switch back to the old protection policies, click **Old Version** on the Protection Settings page.
    -   The new protection policies only support strong cipher suites. Before you switch to the new protection policies, make sure your cipher suite is supported. For more information, see [Cipher suites supported by the new protection policies](#section_yxk_khm_bhb).

## Introduce new protection policies {#section_xbm_bdf_bhb .section}

After you switch to new protection policies, refresh the **Protection Settings** page and you will see the following new features: Geo-blocking, Accurate Access Control, Intelligent Protection, and Web Acceleration Policies.

-   **Geo-blocking**: This feature enables you to block traffic based on geographical location. Chinese regions are divided into 34 provincial regions and international regions are divided into 7 continents. The Anti-DDoS scrubbing center directly discards traffic originating from blocked regions.
-   **Accurate Access Control**: This feature allows you to customize access control rules to filter requests based on the client IP, request URL, and common HTTP header fields, such as the referer, user-agent, and parameter. You can handle matching requests with different actions, such as clear, block, and challenge.
-   **Intelligent Protection**: Based on a big data analysis engine, this feature can analyze your traffic patterns to preemptively detect and block DDoS attacks.
-   **Web Acceleration Policies**: Integrated with Web caching techniques, this feature uses the scrubbing center to speed up your site and protect it from DDoS attacks You can add custom rules to cache specific URLs. Meanwhile, you can select from two cache modes:
    -   **Standard**: Only caches static files on the page, such as .css, .js, and .txt files.
    -   **Enhanced**: Caches all contents on the page.

**Note:** When the beta testing period ends, the configurations of the new protection policies remain effective. You can only enable or disable new features but not change the configurations. To change configurations, you need to buy the new features.

## Cipher suites supported by the new protection policies {#section_yxk_khm_bhb .section}

New protection policies support the following cipher suites:

-   "ECDHE-ECDSA-AES256-GCM-SHA384"
-   "ECDHE-RSA-AES256-GCM-SHA384"
-   "ECDHE-ECDSA-AES128-GCM-SHA256"
-   "ECDHE-RSA-AES128-GCM-SHA256"
-   "ECDHE-ECDSA-WITH-CHACHA20-POLY1305"
-   "ECDHE-RSA-WITH-CHACHA20-POLY1305"
-   "ECDHE-RSA-AES256-CBC-SHA"
-   "ECDHE-RSA-AES128-CBC-SHA"
-   "ECDHE-ECDSA-AES256-CBC-SHA"
-   "ECDHE-ECDSA-AES128-CBC-SHA"

