# Fields {#concept_vkt_t3h_1gb .concept}

In Anti-DDoS Pro, each log entry consists of a wide variety of fields.

You can query and analyze log data on the Full Log page. Field details are as follows:

|Field|Description|Example|
|:----|:----------|:------|
|\_\_topic\_\_|The topic of the log entry. Default value: ddos\_access\_log. You cannot change this value.|-|
|body\_bytes\_sent|The size of the request body. Unit: byte.|2|
|content\_type|The content type of the body of the request.|application/x-www-form-urlencoded|
|host|The domain of the origin server.|api.abc.com|
|http\_cookie|The request cookie.|k1=v1;k2=v2|
|http\_referer|The referer of the request. If this field is empty, `-` is displayed.|http://xyz.com|
|http\_user\_agent|The user agent of the request.|Dalvik/2.1.0 \(Linux; U; Android 7.0; EDI-AL10 Build/HUAWEIEDISON-AL10\)|
|http\_x\_forwarded\_for|The originating IP addresses, including the IP addresses of the client and proxy servers.|-|
|https|Whether the request is an HTTPS request.-   true: The request is an HTTPS request.
-   false: The request is an HTTP request.

|true|
|matched\_host|The domain or wildcard subdomain in the request that matches the domain of the origin server. If no match is found, `-` is displayed.|\*.zhihu.com|
|real\_client\_ip|The actual IP address of the client. If the actual IP address is unavailable, `-` is displayed.|1.2.3.4|
|isp\_line|The network information, such as BGP, China Telecom, and China Unicom.|China Telecom|
|remote\_addr|The client IP address.|1.2.3.4|
|remote\_port|The client port number.|23713|
|request\_length|The length of the request. Unit: byte.|123|
|request\_method|The HTTP request method.|GET|
|request\_time\_msec|The time of the request. Unit: milliseconds.|44|
|request\_uri|The request path.|/answers/377971214/banner|
|server\_name|The domain name in the request. If this field is empty, `default` is displayed.|api.abc.com|
|status|The HTTP status code.|200|
|time|The time when the log entry is written.|2018-05-02T16:03:59+08:00|
|cc\_action|The action that is used to handle the request, such as none, challenge, pass, close, captcha, wait, login, and n.|close|
|cc\_blocks|Whether the request is blocked by HTTP flood protection.-   1: The request is blocked.
-   Otherwise, the request is accepted.

**Note:** In some situations, this field may not exist. The `last_result` field indicates whether the request is blocked by HTTP flood protection.

|1|
|last\_result|Whether the request is blocked by HTTP flood protection.-   ok: The request is accepted.
-   failed: The request fails verification or is blocked.

**Note:** In some situations, this field may not exist. The `cc_blocks` field indicates whether the request is blocked by HTTP flood protection.

|failed|
|cc\_phase|The HTTP flood protection policy that is used, such as seccookie, server\_ip\_blacklist, static\_whitelist, server\_header\_blacklist, server\_cookie\_blacklist, server\_args\_blacklist, and qps\_overmax.|server\_ip\_blacklist|
|ua\_browser|The browser that initiated the request.**Note:** In some situations, this field may not exist.

|ie9|
|ua\_browser\_family|The browser type.**Note:** In some situations, this field may not exist.

|internet explorer|
|ua\_browser\_type|Whether the browser is a Web browser, mobile browser, or other.**Note:** In some situations, this field may not exist.

|web\_browser|
|ua\_browser\_version|The browser version.**Note:** In some situations, this field may not exist.

|9.0|
|ua\_device\_type|The type of the client device.**Note:** In some situations, this field may not exist.

|computer|
|ua\_os|The operating system of the client device.**Note:** In some situations, this field may not exist.

|windows\_7|
|ua\_os\_family|The family of the operating system.**Note:** In some situations, this field may not exist.

|windows|
|upstream\_addr|The list of back-to-origin addresses. The format is `IP:Port`. Multiple addresses are separated by commas \(,\).|1.2.3.4:443|
|upstream\_ip|The actual back-to-origin IP address.|1.2.3.4|
|upstream\_response\_time|The response time when the request is forwarded back to the origin server. Unit: seconds.|0.044|
|upstream\_status|The HTTP status when the request is forwarded back to the origin server.|200|
|user\_id|The Alibaba Cloud account ID.|12345678|
|querystring|The request string.|token=bbcd&abc=123|

